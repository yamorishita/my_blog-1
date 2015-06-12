# my_blog

## コマンド

```bash
$ rails new my_blog
$ cd my_blog
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
