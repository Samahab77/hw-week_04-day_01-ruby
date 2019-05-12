# Ruby HW

![ARRAYS](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQVWBMdo6Ac3moY3tPnzMsFVnOscOR03SxkZ4sPGGhsWoQrYMPZ9g)

## 1. Return an array of each Student's full name, upper-cased

```rb

students = [
  {
      first_name: 'Ahmed',
      last_name: 'Althagafi'
  },
  {
      first_name: 'Norah',
      last_name: 'Alshehri',
  },
  {
      first_name: 'Haneen',
      last_name: 'Alghamdi',
  }
]

upper_case_full_names = []

```

### Answer
```rb
 upper_case_full_names.push(students[0][:first_name]+" "+ students[0][:last_name])

 upper_case_full_names.push(students[1][:first_name]+" "+ students[1][:last_name])

 upper_case_full_names.push(students[2][:first_name]+" "+ students[2][:last_name])

upper_case_full_names
=> ["Ahmed Althagafi", "Norah Alshehri", "Haneen Alghamdi"]

upper_case_full_names.map(&:upcase)
=> ["AHMED ALTHAGAFI", "NORAH ALSHEHRI", "HANEEN ALGHAMDI"]

upper_case_full_names= upper_case_full_names.map(&:upcase)

upper_case_full_names
=> ["AHMED ALTHAGAFI", "NORAH ALSHEHRI", "HANEEN ALGHAMDI"]
```

```rb

[ 'AHMED ALTHAGAFI', 'NORAH ALSHEHRI', 'HANEEN ALGHAMDI' ]

```

## 2. Find the first order for each user

```rb

users = [
  {
      name: 'Salman',
      orders: [
          {
              description: 'a bike'
          }
      ]
  },
  {
      name: 'Saeed',
      orders: [
          {
              description: 'bees'
          },
          {
              description: 'fishing rod'
          }
      ]
  },
  {
      name: 'Danyah',
      orders: [
          {
              description: 'a MacBook'
          },
          {
              description: 'The West Wing DVDs'
          },
          {
              description: 'headphones'
          },
          {
              description: 'a kitten'
          }
      ]
  }
]

first_order_for_each_user = []

```

### Answer
```rb
first_order_for_each_user = []

  first_order_for_each_user.push(users[0][:orders][0])
=> [{:description=>"a bike"}]
first_order_for_each_user.push(users[1][:orders][0])
=> [{:description=>"a bike"}, {:description=>"bees"}]
first_order_for_each_user.push(users[2][:orders][0])
=> [{:description=>"a bike"}, {:description=>"bees"}, {:description=>"a MacBook"}]
first_order_for_each_user 
=> [{:description=>"a bike"}, {:description=>"bees"}, {:description=>"a MacBook"}, {:description=>"a bike"}]

```
```rb

[ {description: "a bike"}, {description: "bees"}, {description: "a MacBook"} ]
```

## 3. Find the average amount spent on coffee, per transaction, for each person

```rb

people = [
  {
      name: 'Jawaher',
      transactions: [
          {
              type: 'COFFEE',
              amount: 7.43
          },
          {
              type: 'TACOS',
              amount: 14.65
          },
          {
              type: 'COFFEE',
              amount: 4.43
          }
      ]
  },
  {
      name: 'Nader',
      transactions: [
          {
              type: 'BIKES',
              amount: 800.00
          },
          {
              type: 'TACOS',
              amount: 14.65
          },
          {
              type: 'COFFEE',
              amount: 4.43
          }
      ]
  },
  {
      name: 'Samah',
      transactions: [
          {
              type: 'COFFEE',
              amount: 7.43
          },
          {
              type: 'COFFEE',
              amount: 100.00
          },
          {
              type: 'COFFEE',
              amount: 4.43
          }
      ]
  }
]


coffee_average_per_person = []

```

### Answer

- finding the ave for every person
then creat hash for every one 
then push them inside the array 

```rb 
(people[0][:transactions][0][:amount]+people[0][:transactions][2][:amount])/2
=> 5.93

- creat hash for every people
p1= {}
p1[:name]=people[0][:name]
p1[:coffee_average]=(people[0][:transactions][0][:amount]+people[0][:transactions][2][:amount])/2
=> 5.93]
p1 
=> {:name=>"Jawaher", :coffee_average=>5.93}

p2={}
p2[:name]=people[1][:name]
=> "Nader"
p2[:coffee_average]=(people[1][:transactions][2][:amount])/1
=> 4.43

p3={name:people[2][:name], coffee_average: (people[2][:transactions][0][:amount]+people[2][:transactions][1][:amount]+people[2][:transactions][2][:amount])/people[2][:transactions].size}

 p3
=> {:name=>"Samah", :coffee_average=>37.28666666666667}

coffee_average_per_person.push(p1,p2,p3)
 coffee_average_per_person 
=> [{:name=>"Jawaher", :coffee_average=>5.93},
 {:name=>"Nader", :coffee_average=>4.43},
 {:name=>"Samah", :coffee_average=>37.28666666666667}]

```




```rb

[ 
  {name: "Jawaher", :coffee_average=>5.93}, 
  {name: "Nader", :coffee_average=>4.43}, 
  {name: "Samah", :coffee_average=>37.28666666666667} 
]

```

## 4. Find the most expensive product for each store, with the store name:

```rb

stores = [
  {
      store_name: 'Jarir',
      products: [
          {
              description: 'Titanium',
              price: 9384.33
          },
          {
              description: 'Gold',
              price: 345.54
          }
      ]
  },
  {
      store_name: 'Danub',
      products: [
          {
              description: 'Silver',
              price: 654.44
          },
          {
              description: 'Ruby',
              price: 323.43
          }
      ]
  },
  {
      store_name: 'Souq',
      products: [
          {
              description: 'Opal',
              price: 345.43
          },
          {
              description: 'Sapphire',
              price: 899.33
          }
      ]
  }
]

most_expensive_products_by_store = []

```

### Answer

```rb

[ 
  {store_name: "Jarir", most_expensive_product: { description: "Titanium", price: 9384.33}},
  {store_name: "Danub", most_expensive_product: { description: "Silver", price: 654.44}},
  {store_name: "Souq", most_expensive_product: { description: "Sapphire", price: 899.33}}
]
```

# Bonus

Write an infinite loop that will make you add all the your friends in the students list and after each add will ask if you want to quit the loop (yes/no) if the user choose no print all the students array

### Answer

```

>add a student
Sumayah Bahkeem
>Do you want to continue ? (y/n)
y
>add a student
Huda Binzaqr
>Do you want to continue ? (y/n)
y
>add a student

```
