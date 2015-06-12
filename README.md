# my_blog
仕様は課題ページを参照のこと。

## 手順
### プロジェクト作成

```bash
$ rails new my_blog
$ cd my_blog
```

### モデル生成

```bash
$ rails g model post title:string body:text category:string
      invoke  active_record
      create    db/migrate/20150612091732_create_posts.rb
      create    app/models/post.rb
      invoke    test_unit
      create      test/models/post_test.rb
      create      test/fixtures/posts.yml
$ rails g model author name:string description:string image_url:string
      invoke  active_record
      create    db/migrate/20150612091740_create_authors.rb
      create    app/models/author.rb
      invoke    test_unit
      create      test/models/author_test.rb
      create      test/fixtures/authors.yml
$ rake db:migrate
== 20150612091732 CreatePosts: migrating ======================================
-- create_table(:posts)
   -> 0.0014s
== 20150612091732 CreatePosts: migrated (0.0015s) =============================

== 20150612091740 CreateAuthors: migrating ====================================
-- create_table(:authors)
   -> 0.0009s
== 20150612091740 CreateAuthors: migrated (0.0010s) ===========================
```

### コントローラ生成

```bash
$ rails g controller posts index show new create edit update destroy
      create  app/controllers/posts_controller.rb
       route  get 'posts/destroy'
       route  get 'posts/update'
       route  get 'posts/edit'
       route  get 'posts/create'
       route  get 'posts/new'
       route  get 'posts/show'
       route  get 'posts/index'
      invoke  erb
      create    app/views/posts
      create    app/views/posts/index.html.erb
      create    app/views/posts/show.html.erb
      create    app/views/posts/new.html.erb
      create    app/views/posts/create.html.erb
      create    app/views/posts/edit.html.erb
      create    app/views/posts/update.html.erb
      create    app/views/posts/destroy.html.erb
      invoke  test_unit
      create    test/controllers/posts_controller_test.rb
      invoke  helper
      create    app/helpers/posts_helper.rb
      invoke    test_unit
      invoke  assets
      invoke    coffee
      create      app/assets/javascripts/posts.coffee
      invoke    scss
      create      app/assets/stylesheets/posts.scss
```

### Authorデータ作成

```
$ rails c
irb(main):001:0> Author.create(name: 'sparta', description: 'hogehoge', image_url: 'http://www.nobodyeverdrownedinsweat.com/wp-content/uploads/2012/02/spartan-cam-logo1.png')
   (0.1ms)  begin transaction
  SQL (1.3ms)  INSERT INTO "authors" ("name", "description", "image_url", "created_at", "updated_at") VALUES (?, ?, ?, ?, ?)  [["name", "sparta"], ["description", "hogehoge"], ["image_url", "http://www.nobodyeverdrownedinsweat.com/wp-content/uploads/2012/02/spartan-cam-logo1.png"], ["created_at", "2015-06-12 09:26:20.091677"], ["updated_at", "2015-06-12 09:26:20.091677"]]
   (0.7ms)  commit transaction
=> #<Author id: 1, name: "sparta", description: "hogehoge", image_url: "http://www.nobodyeverdrownedinsweat.com/wp-content...", created_at: "2015-06-12 09:26:20", updated_at: "2015-06-12 09:26:20">
```
