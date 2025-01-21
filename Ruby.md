```
class PostsController < ApplicationController
  def index
    @posts = Post.all.order(created_at: :desc)
  end
  
  def show
    @post = Post.find_by(id: params[:id])
  end
  
  def new
  end
  
  def create
    @post = Post.new(content: params[:content])
    @post.save
    redirect_to("/posts/index")
  end
  
  def edit
    @post = Post.find_by(id: params[:id])
  end
  
  def update
    # updateアクションの中身を作成してください
    @post = Post.find_by(id:params[:id])
    @post.content = params[:content]
    @post.save
    redirect_to("/posts/index")
  end
  
end
```
```
class UsersController < ApplicationController
  def index
    @users = User.all
  end
  
  def show
    @user = User.find_by(id: params[:id])
  end
  
  def new
    @user = User.new
  end
  
  def create
    @user = User.new(
      name: params[:name],
      email: params[:email],
      image_name: "default_user.jpg"
    )
    if @user.save
      flash[:notice] = "ユーザー登録が完了しました"
      redirect_to("/users/#{@user.id}")
    else
      render("users/new")
    end
  end
  
  def edit
    @user = User.find_by(id: params[:id])
  end
  
  def update
    @user = User.find_by(id: params[:id])
    @user.name = params[:name]
    @user.email = params[:email]
    if params[:image]
    # 画像を保存する処理を追加してください
    @user.image_name = "#{@user.id}.jpg"
    image = params[:image]
    File.binwrite("public/user_images/#{@user.image_name}",image.read)
    
    if @user.save
      flash[:notice] = "ユーザー情報を編集しました"
      redirect_to("/users/#{@user.id}")
    else
      render("users/edit")
    end
  end
  
end
```
```
class User < ApplicationRecord
  validates :name, {presence: true}
  validates :email, {presence: true, uniqueness: true}
  # passwordカラムにバリデーションを設定してください
  validates :password, {presence: true} 
  
end
```
```
class AddPasswordToUsers < ActiveRecord::Migration[5.0]
  def change
    add_column :users,:password,:string
  end
end
```
