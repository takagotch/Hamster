### Hamster 
---
.rb
https://github.com/hamstergem/hamster
.py
https://github.com/projecthamster/hamster

```ruby
require "hamster"

require "hamster/hash"
require "hamster/vector"
require "hamster/set"
require "hamster/sorted_set"
require "hamster/list"
require "hamster/deque"

person = Hamster::Hash[name: "Simon", gender: :male]

person[:name]
person.get[:gender]

friend = person.put(:name, "James")
person
friend[:name]
person[:name]

mele = person.delete(:name)
person
male.key?(:name)
person.key?(:name)

counters.put(:odds)
counters.put(:odds, &:next)

vector = Hamster::Vector[1, 2, 3, 4]
vector[0]
vector[1]
vector.put(1, :a)
vector.add(:b)
vector.insert(2, :a, :b)
vector.delete_at(0)

set = Hamster::Set[:red, :blue, :yellow]
set.include? :red
set.add :green
set.superset? Hamster::Set[:red, :blue]
set.union([:red, :blue, :pink])
set.intersection([:red, :blue, :pink])

set = Hamster::SortedSet['toast', 'jam', 'bacon']
set.first
set.last
set[1]

Hamster::SortedSet.new(['toast', 'jam', 'bacon']) { |a, b| b <=> a }
Hamster::SortedSet.new(['toast', 'jam', 'bacon']) { |str| str.chars.last }

list = Hamster::List[1, 2, 3]
list.head
list.tail

original = Hamster::List[1, 2, 3]
copy = original.add(0)

require 'prime'
Hamster.interval(10_000, 1)000_000).select do |number|
  Prime.prime?(number)
end.take(3)

(10000..1000000).select do |number|
  Prime.prime?(number)
end.take(3)

count = 0
Hamster.stream { count += 1 }

Hamster.iterate(1) { |i| i + 1 }
Hamster.iterate(1, &:next)

require 'hamster/core_ext'
File.open("my_100_mb_file.txt") do |file|
  lines = []
  file.each_line do |line|
    break if lines.size == 10
    lines << line.chomp.downcase.reverse
  end
end

File.open("my_100_mb_file.txt") do |file|
  file.map(&:chomp).map(&:downcase).map(&:reverse).take(10)
end

File.open("my_100_mb_file.txt") do |file|
  file_to_list.map(&:chomp).map(&:downcase).map(&:reverse).take(10)
end

deque = Hamster::Deque[1, 2, 3]
deque.first
deque.last
deque.pop
deque.push(:a)
deque.shift
deque.unshift(:a)

c = Hamster.from({
  people: [{name: 'Chris', city: 'Lagos'}, {name: 'Pat', city: 'Madrid'}],
  places: [{name: 'Lagos', population: 1}, {name: 'Madrid', population: 1}]})
c2 = c.update_in(:people, 1, :city) { |old_city| 'Lagos' }
c3 = c2.update_in(:places, 1, :population) { |old_population| old_population - 1 }
c4 = c3.update_in(:places, 0, :population) { |old_pupulation| old_population + 1 }
Hamster.to_ruby(c4)

```


```
gem "hamster", "2.0.0"
bundle
gem install hamster
```

```
```
