docker pull mongo

docker run -d -p 27017:27017 --name m1 mongo

pip install pymongo

import pymongo  # package for working with MongoDB
client = pymongo.MongoClient("mongodb://localhost:27017/")
db = client["customersdb"]
customers = db["customers"]
customers_list = [
  { "name": "Amy", "address": "Apple st 652"},
  { "name": "Hannah", "address": "Mountain 21"},
  { "name": "Michael", "address": "Valley 345"},
  { "name": "Sandy", "address": "Ocean blvd 2"},
  { "name": "Betty", "address": "Green Grass 1"},
  { "name": "Richard", "address": "Sky st 331"},
  { "name": "Susan", "address": "One way 98"},
  { "name": "Vicky", "address": "Yellow Garden 2"},
  { "name": "Ben", "address": "Park Lane 38"},
  { "name": "William", "address": "Central st 954"},
  { "name": "Chuck", "address": "Main Road 989"},
  { "name": "Viola", "address": "Sideway 1633"}
]
x = customers.insert_many(customers_list)
# print list of the _id values of the inserted documents:
print(x.inserted_ids)

import pymongo
client = pymongo.MongoClient("mongodb://localhost:27017/")
db = client["customersdb"]
customers = db["customers"]
for x in customers.find():
    print(x)

mongoexport --db compared_info_db --collection mobile_phones | sed '/"_id":/s/"_id":[^,]*,//' > file_name.json
docker cp d25254a605b2:/file_name.json ~/Downloads/
mongoexport --db compared_data_db --collection mobile_phones_2020-04-26 --jsonArray --out mobile_phones_2020-04-26.json

https://medium.com/codervlogger/python-mongodb-tutorial-using-docker-52f330852b4c
