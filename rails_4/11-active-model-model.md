!SLIDE bullets incremental
# ActiveModel::Model
    @@@ ruby
    class Contact
      include ActiveModel::Model
      attr_accessor :name, :email, :message
      validates :name, presence: true
    end

!SLIDE bullets incremental
# ActiveModel::Model
* Validations
* Conversions (to\_param, to\_model, to\_key)
* Naming (model_name, singular, plural)
* Translation
