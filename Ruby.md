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
