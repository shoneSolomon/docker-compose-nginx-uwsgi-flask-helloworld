## Create a dataset

```
POST /datasets
{
    "name": "dataset_name",
    "type": "product"
}
```

## List datasets

```
GET /datasets
```

### parameters

* query: dataset_name prefix search
* sort: a for asc, d for desc
* state: deleted or not

``` 
GET /datasets?query=prefix&sort=a&state=deleted
```

## Get a dataset

``` 
GET /datasets/<dataset_name>
```

## Delete a dataset

``` 
DELETE /datasets/<dataset_name>
```

note: 第一次 DELETE 为 soft delete，第二次 DELETE 为真正从数据库中删除。


## Create a product

```
POST /datasets/<dataset_name>/items
{
    "product_id": "origin_product_id",
    "name": "product_name",
    "category": "category",
    "images": [
        "http://1.jpg",
        "https://2.jpg"
    ],
    "attributes": [
        {"k": "key1", "v": "value1"},
        {"k": "key2", "v": "value2"},
    ]
}
```

## List products

``` 
GET /datasets/<dataset_name>/items
```

## Get a product

``` 
GET /datasets/<dataset_name>/items/<item_id>
```

## Update a product

``` 
PATCH /datasets/<dataset_name>/items/<item_id>
```

## Delete a product

```
DELETE /datasets/<dataset_name>/items/<item_id>
```



# TODO

* ~~check x-consumer-custom-id by decorator~~


* ~~list datasets~~
* ~~datasets pagination~~
* ~~datasets query by name~~
* ~~datasets order by created_at~~
* ~~datasets deleted filter~~
* ~~dataset name unique~~
* ~~get dataset by name~~
* ~~datasets soft delete~~
* ~~datasets real delete~~


* ~~list products~~
* ~~get product by name~~
* ~~products pagination~~
* ~~product id unique~~
* ~~product multi images~~
* ~~product attributes~~


* ~~404 errors~~


* entity transform
