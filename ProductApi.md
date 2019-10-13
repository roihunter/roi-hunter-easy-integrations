# Product API

#### [GET] /products?page={page-number}&limit={max-items-per-page}&changed-since={date}

```JSON
{
 "id": "12345",
 "base_product_id": "789",
 "price": 12.99,
 "compare_at_price": 19.99,
 "currency": "USD",
 "title": "iPhone cover black",
 "description": "Product description",
 "primary_category": "Cell Phone Accessories > Covers",
 "cover_image": "https://myshop.com/image.png",
 "additional_images": [
   "https://myshop.com/image1.png",
   "https://myshop.com/image2.png"
 ],
 "inventory_quantity": 10,
 "last_updated_at": "2019-10-10T16:33:11+02:00"
}
```
