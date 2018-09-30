### acts_as_follower
---


https://github.com/tcocca/acts_as_follower

```sh
gem 'acts_as_follower', github: 'tcocca/acts_as_follower', branch: 'master'
gem "acts_as_follower"
rails g acts_as_follower

gem "acts_as_follower", '~> 0.1.1'
gem "acts_as_follower", git: 'git://github.com/tcocca/acts_as_follower.git', branch: 'rails3'
rails g acts_as_follower

script/plugin install git://github.com/tcacca/acts_as_follower.git -r rails_2.3.x
script/generate acts_as_follower
```


```ruby
class User < ActiveRecord::Base
  acts_as_followable
end
class Book < ActiveRecord::Base
  acts_as_followable
end
class User < ActiveRecord::Base
  acts_as_follower
end

book = Book.find(1)
user = User.find(1)
user.follow(book)

user.stop_following(book)
user.following?(book)
user.all_follows
user.all_following
user.following_by_type('Book')
user.following_by_type_count('Book')
user.follows_scoped
follows_by_type, all_follows, all_following, following_by_type
book.followers
book.followers_scoped
book.followers_by_type('User')
book.followers_by_type_count('User')
book.followed_by?(user)
book.block(user)
book.unclock(user)
book.blocks
book.blocked_followers_count
followers_by_type, followers, blocks

# Follow Model
Follow.unblocked
Follow.blocked
Follow.descending

Follow.recent
Follow.recent(4.weeks.ago)

Follow.for_follower(user)

user.all_follows
User.all_following

Follow.for_followable(book)
book.followers

book.blocks

```

