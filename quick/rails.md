# Rails

- [Reference Docs](https://api.rubyonrails.org/)
- [Guides](https://guides.rubyonrails.org/)

## ActiveRecord

### ActiveRecord::AttributeMethods::Read

#### Read type-casted value from DB

This is helpful if you have a custome reader method that you want to circumvent, like for tests.

[Docs](https://api.rubyonrails.org/classes/ActiveRecord/AttributeMethods/Read.html#method-i-read_attribute)

<dl>
  <dt>read_attribute(attr_name, &block)</dt>
  <dd>Returns the value of the attribute identified by attr_name after it has been typecast (for example, “2004-12-12” in a date column is cast to a date object, like Date.new(2004, 12, 12)).</dd>
</dl>

## ActiveSupport

### ActiveSupport::Logger

#### Broadcast to multiple loggers

[Code](https://github.com/rails/rails/blob/7-0-stable/activesupport/lib/active_support/logger.rb#L22-L23)

```ruby
new_logger = Logger.new(StringIO.new)

Rails.logger.extend(ActiveSupport::Logger.broadcast(new_logger))
```

### Array

#### Array.wrap vs Kernel#Array

Array.wrap only coerces with `#to_ary` and does not type checking.

Kerenl#Array calls `to_ary`, then `#to_a`, and type checks to ensure it's either `nil` or an `Array`.

[Array.wrap vs Kernel#Array]([url](https://www.mendelowski.com/docs/ruby/array-wrap-vs-kernel-array/))
