#Chat-SpaceDB設計

##Users_table

###association

* has_many :user_groups
* has_many :groups, through: :user_groups
* has_many :messages

###column

* t.integer :id
* t.string  :name
* t.string  :email
* t.string  :password

## User_groups_table

###association

* belongs_to :user
* belongs_to :group

### column

* t.integer :id
* t.references :user
* t.references :group

## Groups_table

###association

* has_many :user_groups
* has_many :users, through: :user_groups
* has_many :messages

### column

* t.integer :id
* t.string :name

## Messages_table

###association
* message belongs_to :user
* message belongs_to :group

###column

* t.integer :id
* t.text :body
* t.string :image
* t.references :user
* t.references :group
