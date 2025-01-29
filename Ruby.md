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
```
<div class="main users-new">
  <div class="container">
    <div class="form-heading">ログイン</div>
    <div class="form users-form">
      <div class="form-body">
        <!-- form_tagメソッドを追加してください -->
        <%= form_tag("/login") do %>
          <p>メールアドレス</p>
          <!-- name属性を追加してください -->
          <input name="email">
          <p>パスワード</p>
          <!-- name属性を追加してください -->
          <input type="password" name="password">
          <input type="submit" value="ログイン">
        <!-- form_tag用のendを追加してください -->
        <%end%>
      </div>
    </div>
  </div>
</div>
```
```
<!DOCTYPE html>
<html>
  <head>
    <title>TweetApp</title>
    <%= csrf_meta_tags %>

    <%= stylesheet_link_tag    'application', media: 'all', 'data-turbolinks-track': 'reload' %>
    <%= javascript_include_tag 'application', 'data-turbolinks-track': 'reload' %>
  </head>

  <body>
    <header>
      <div class="header-logo">
        <%= link_to("TweetApp", "/") %>
      </div>
      <ul class="header-menus">
        <!-- 以下の1行を削除してください -->
        
        <!-- @current_userに書き換えてください -->
        <% if @current_user %>
          <li>
            <!-- @current_userに書き換えてください -->
            <%= link_to(@current_user.name, "/users/#{@current_user.id}") %>
          </li>
          <li>
            <%= link_to("投稿一覧", "/posts/index") %>
          </li>
          <li>
            <%= link_to("新規投稿", "/posts/new") %>
          </li>
          <li>
            <%= link_to("ユーザー一覧", "/users/index") %>
          </li>
          <li>
            <%= link_to("ログアウト", "/logout", {method: "post"}) %>
          </li>
        <% else %>
          <li>
            <%= link_to("TweetAppとは", "/about") %>
          </li>
          <li>
            <%= link_to("新規登録", "/signup") %>
          </li>
          <li>
            <%= link_to("ログイン", "/login") %>
          </li>
        <% end %>
      </ul>
    </header>

    <% if flash[:notice] %>
      <div class="flash">
        <%= flash[:notice] %>
      </div>
    <% end %>
    
    <%= yield %>
  </body>
</html>
```
