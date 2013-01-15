!SLIDE
# ActiveRecord.new

!SLIDE bullets incremental
# drop\_table and remove\_column are now reversible
# Identity map removed

!SLIDE
# Model#all returns an relation rather than an array

## 3.x
    @@@ ruby
    Model.all # => [...]
    Model.all.where
    # => undefined method `where' for #<Array:0x0..>

## 4.0
    @@@ ruby
    Model.all # => ActiveRecord::Relation
    Model.all.where # => ActiveRecord::Relation

!SLIDE
# include\_root\_in\_json = false

## 3.x
    @@@ ruby
    [
      { person:{name: "John Smith"} }
    ]

## 4.0
    @@@ ruby
    [
      {name: "John Smith"}
    ]

!SLIDE smaller
# Callable scope objects
## 3.x
    @@@ ruby
    scope :recent, where(published_at: Time.now - 2.weeks
## 4.0
    @@@ ruby
    scope :recent,  ->{where(published_at: Time.now - 2.weeks)}

!SLIDE
# .not
    @@@ ruby
    Article.where.not(title: 'Rails 3')
