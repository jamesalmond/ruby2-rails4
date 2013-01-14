!SLIDE bullets incremental
# ActiveModel::Model

    @@@ ruby
    class Contact
      include ActiveModel::Model
      attr_accessor :name, :email, :message
      validates :name, presence: true
    end
* Validations
* Conversions (to_param, to_model, to_key)
* Naming (model_name, singular, plural)
* Translation
