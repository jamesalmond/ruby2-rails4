!SLIDE
# Enumerator#lazy

!SLIDE execute

    @@@ ruby
    ['a b', 'c d'].map(&:split).map(&:reverse)

!SLIDE execute

    @@@ ruby
    ['a b', 'c d'].lazy.
    map(&:split).map(&:reverse).class

!SLIDE execute

    @@@ ruby
    ['a b', 'c d'].lazy.
    map(&:split).map(&:reverse).to_a

.notes But actually this isn't any faster in most instances. the
overhead of the way laxy creates blocks slows the iterators down
