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
***
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
```
<div class="main user-show">
  <div class="container">
    <div class="user">
      <img src="<%= "/user_images/#{@user.image_name}" %>">
      <h2><%= @user.name %></h2>
      <p><%= @user.email %></p>
      <!-- @userのidとLog Inしているユーザーのidが等しい場合のみ、以下のリンクを表示してください -->
      <% if @user.id == @current_user.id %>
      <%= link_to("編集", "/users/#{@user.id}/edit") %>
    </div>
  </div>
</div>
```
```
Rails.application.routes.draw do
   get "login" => "users#login_form"
  post "users/:id/update" => "users#update"
  get "users/:id/edit" => "users#edit"
  post "users/create" => "users#create"
  get "signup" => "users#new"
  get "users/index" => "users#index"
  get "users/:id" => "users#show"

  get "posts/index" => "posts#index"
  get "posts/new" => "posts#new"
  get "posts/:id" => "posts#show"
  post "posts/create" => "posts#create"
  get "posts/:id/edit" => "posts#edit"
  post "posts/:id/update" => "posts#update"
  post "posts/:id/destroy" => "posts#destroy"
  
  get "/" => "home#top"
  get "about" => "home#about"
end
```
```
<div class="main users-new">
  <div class="container">
    <div class="form-heading">ログイン</div>
    <div class="form users-form">
      <div class="form-body">
        <% if @error_message %>            
            <div class="form-error">            
            <%= @error_message %>            
            </div>            
         <% end %>
        <%= form_tag("/login") do %>            
<p>メールアドレス</p>  
<input name="email" value="<%= @email %>">
<p>パスワード</p>
<input type="password" name="password" value="<%= @password %>">  
<input type="submit" value="ログイン">
<% end %>
      </div>
    </div>
  </div>
</div>
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
      image_name: "default_user.jpg",
      password: params[:password]
      )
    if @user.save
      session[:user_id] = @user.id
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
             @user.image_name = "#{@user.id}.jpg"
             image = params[:image]
              File.binwrite("public/user_images/#{@user.image_name}", image.read)      
             end
    if @user.save
      flash[:notice] = "ユーザー情報を編集しました"
      redirect_to("/users/#{@user.id}")
    else
      render("users/edit")
    end
  end
 def login_form
 end
 
 def login         
 @user = User.find_by(email: params[:email], password: params[:password])
   if @user
  session[:user_id] = @user.id
   flash[:notice] = "ログインしました"
    redirect_to("/posts/index")
       else
         @error_message = "メールアドレスまたはパスワードが間違っています"
         @email = params[:email]
         @password = params[:password]
      render("users/login_form")
      end         
      end
end
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
        <% if session[:user_id] %>       
            <li>       
            現在ログインしているユーザーのid:  
            <%= session[:user_id] %>     
            </li>       
      <%= link_to("投稿一覧", "/posts/index") %>        
       </li>    
       <li>  
        <%= link_to("新規投稿", "/posts/new") %>    
       </li>
       <li>
        <%= link_to("ユーザー一覧", "/users/index") %>       
       </li>     
        <li>       
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
        <!-- 現在ログイン中のユーザーを取得し、変数current_userに代入してください -->
        <% current_user = User.find_by(id: session[:user_id]) %>
        
        <!-- if文の条件を書き換えてください -->
        <% if current_user %>
          <li>
            <!-- 以下の「現在しているユーザーのid:」を削除してください -->
            
            <!-- Log In中のユーザーの名前を表示し、詳細ページのリンクとなるように書き換えてください -->
            <%= link_to(current_user.name, "/users/#{current_user.id}") %>
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
```
class ApplicationController < ActionController::Base
before_action :set_current_user
   def set_current_user
   @current_user = User.find_by(id: session[:user_id])
   end
   def authenticate_user
     if @current_user == nil
       flash[:notice] = "ログインが必要です"
       redirect_to("/login")
      end
    end
    def forbid_login_user
    if @current_user 
      flash[:notice] = "すでにログインしています"
      redirect_to("/posts/index")
    end
  end
end
```
```
class UsersController < ApplicationController
  before_action :authenticate_user, {only: [:index, :show, :edit, :update]}
  before_action :forbid_login_user, {only: [:new, :create, :login_form, :login]}
  before_action:ensure_correct_user, {only: [:edit, :update]}

  
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
      image_name: "default_user.jpg",
      password: params[:password]
      )
    if @user.save
      session[:user_id] = @user.id
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
             @user.image_name = "#{@user.id}.jpg"
             image = params[:image]
              File.binwrite("public/user_images/#{@user.image_name}", image.read)      
             end
    if @user.save
      flash[:notice] = "ユーザー情報を編集しました"
      redirect_to("/users/#{@user.id}")
    else
      render("users/edit")
    end
  end
 def login_form
 end
 
 def login         
 @user = User.find_by(email: params[:email], password: params[:password])
   if @user
  session[:user_id] = @user.id
   flash[:notice] = "ログインしました"
    redirect_to("/posts/index")
       else
         @error_message = "メールアドレスまたはパスワードが間違っています"
         @email = params[:email]
         @password = params[:password]
      render("users/login_form")
      end    
end
def logout 
  session[:user_id] = nil 
  flash[:notice] = "ログアウトしました"
    redirect_to("/login")
end
def ensure_correct_user
   if @current_user.id != params[:id].to_i
    flash[:notice] = "権限がありません"
    redirect_to("/posts/index")
  end
end
end
```
```
<div class="main posts-index">
  <div class="container">
    <% @posts.each do |post| %>
      <div class="posts-index-item">
        <div class="post-left">
          <!-- ユーザーの画像が表示されるように、以下のsrcに値を追加してください -->
          <img src="<%= "/user_images/#{post.user.image_name}" %>">
        </div>
        <div class="post-right">
          <div class="post-user-name">
            <!-- link_toメソッドを用いて、ユーザー詳細ページへのリンクを作成してください -->
            <%= link_to(post.name, "/users/#{post.id}") %>
          </div>
          <%= link_to(post.content, "/posts/#{post.id}") %>
        </div>
      </div>
    <% end %>
  </div>
</div>
```
```
<div class="main user-show">
  <div class="container">
    <div class="user">
      <img src="<%= "/user_images/#{@user.image_name}" %>">
      <h2><%= @user.name %></h2>
      <p><%= @user.email %></p>
      <% if @user.id == @current_user.id %>
        <%= link_to("編集", "/users/#{@user.id}/edit") %>
      <% end %>
    </div>
    <!-- 以下の<% @user.posts.each do |post|%>を使ってeach文を追加してください -->
    <% %>
      <!-- 指定されたコードを貼り付けてください -->
       <div class="posts-index-item">
        <div class="post-left">
          <img src="<%= "/user_images/#{post.user.image_name}" %>">
        </div>
        <div class="post-right">
          <div class="post-user-name">
            <%= link_to(post.user.name, "/users/#{post.user.id}") %>
          </div>
          <%= link_to(post.content, "/posts/#{post.id}") %>
        </div>
      </div>
    <!-- 以下の<% %>を使ってeach文のendを追加してください -->
    <% end %>
  </div>
</div>
```
```
<div class="main posts-show">
  <div class="container">
    <div class="posts-show-item">
      <div class="post-user-name">
        <img src="<%= "/user_images/#{@user.image_name}" %>">
        <%= link_to(@user.name, "/users/#{@user.id}") %>
      </div>
      <p>
        <%= @post.content %>
      </p>
      <div class="post-time">
        <%= @post.created_at %>
      </div>
      <!-- 以下の<% %>を使ってif文を追加してください -->
      <% if @post.user_id == @current_user.id %>
        <div class="post-menus">
          <%= link_to("編集", "/posts/#{@post.id}/edit") %>
          <%= link_to("削除", "/posts/#{@post.id}/destroy", {method: "post"}) %>
        </div>
      <!-- 以下の<% %>を使ってif文のendを追加してください -->
      <% end %>
    </div>
  </div>
</div>
```
```
class PostsController < ApplicationController
  before_action :authenticate_user
  # before_actionでensure_correct_userメソッドを指定してください
  
  
  def index
    @posts = Post.all.order(created_at: :desc)
  end
  
  def show
    @post = Post.find_by(id: params[:id])
    @user = @post.user
  end
  
  def new
    @post = Post.new
  end
  
  def create
    @post = Post.new(
      content: params[:content],
      user_id: @current_user.id
    )
    if @post.save
      flash[:notice] = "投稿を作成しました"
      redirect_to("/posts/index")
    else
      render("posts/new")
    end
  end
  
  def edit
    @post = Post.find_by(id: params[:id])
  end
  
  def update
    @post = Post.find_by(id: params[:id])
    @post.content = params[:content]
    if @post.save
      flash[:notice] = "投稿を編集しました"
      redirect_to("/posts/index")
    else
      render("posts/edit")
    end
  end
  
  def destroy
    @post = Post.find_by(id: params[:id])
    @post.destroy
    flash[:notice] = "投稿を削除しました"
    redirect_to("/posts/index")
  end
  
  # ensure_correct_userメソッドを定義してください
  def ensure_correct_user
  @pos = Post.find_by(id: params[:id])
  flash[:notice] = "権限がありません"
      redirect_to("/posts/index")
end
  
  
end
```
```
class Like < ApplicationRecord
  validates:user_id,{presence:ture}
  validates:post_id,{presence:ture}
end
```
