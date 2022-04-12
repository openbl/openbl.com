# FactoryBot

- [Docs](https://github.com/thoughtbot/factory_bot/blob/master/GETTING_STARTED.md)

## Transient

```ruby
factory :user do
  transient do
    rockstar { true }
  end

  name { "John Doe#{" - Rockstar" if rockstar}" }
end

create(:user).name
#=> "John Doe - ROCKSTAR"

create(:user, rockstar: false).name
#=> "John Doe"
```