# E-commerce Backend Server

- [Description](#description)
- [Installation](#installation)
- [Usage](#usage)
  - [Category API](#category-api)
  - [Product API](#product-api)
  - [Tag API](#tag-api)
- [Contribution](#contribution)
- [License](#license)

## Description

Server-side application for a e-commerce application to manage products. Build with `ExpressJS` and `Sequelize`.

## Installation

> 1. Use `git clone https://github.com/hmhtom/e-commerce-backend.git` to clone the repository under your local
> 2. Go to the root folder of the repository
> 3. Make sure `Node` is installed on your computer
> 4. Run `npm install` to install the dependencies
> 5. Login to your database in console, use `source db/schema.sql` to create new database.
> 6. Make sure your `.env` file contains `DB_NAME='ecommerce_db'`, `DB_USER=<database user name>` and `DB_PASSWORD=<database password>`
> 7. Run `npm run seed` to apply test seeds to database.
> 8. Run `npm start` to start the server.

## Usage

[Here is a walkthrough video to the application](https://drive.google.com/file/d/1XHGBxC_7cQe8egruYfcvvcZojrnE6hFk/view)

Once the server is running, api calls are available through following api routes:

### Category API

- Get all categories: get `/categories`

```JSON
[
    {
        id,
        category_name,
        products : [
            {
               id,
               product_name,
               price,
               stock,
               category_id
            },
            ...
        ]

    },
     ...
]
```

- Get category by id: get `/categories/:id`

```JSON
    {
        id,
        category_name,
        products : [
            {
               id,
               product_name,
               price,
               stock,
               category_id
            },
            ...
        ]

    }
```

- Create new category: post `/categories`
- Update category by id: put `/categories/:id`
- Delete category by id: delete `/categories/:id`

### Product API

- Get all categories: get `/products`

```JSON
[
    {
        id,
        product_name,
        price,
        stock,
        category_id,
        category:{
            id,
            category_name
        },
        tags : [
            {
                id,
                tag_name,
                product_tag :{
                    id,
                    product_id,
                    tag_id
                }
            },
            ...
        ]

    },
     ...
]
```

- Get category by id: get `/products/:id`

```JSON
    {
        id,
        product_name,
        price,
        stock,
        category_id,
        category:{
            id,
            category_name
        },
        tags : [
            {
                id,
                tag_name,
                product_tag :{
                    id,
                    product_id,
                    tag_id
                }
            },
            ...
        ]

    }
```

- Create new category: post `/products`
- Update category by id: put `/products/:id`
- Delete category by id: delete `/products/:id`

### Tag API

- Get all categories: get `/tags`

```JSON
[
    {
        id,
        tag_name,
        products:[
            {
                id,
                product_name,
                price,
                stock,
                category_id,
                product_tag :{
                    id,
                    product_id,
                    tag_id
                }
            },
            ...
        ]

    },
     ...
]
```

- Get category by id: get `/tags/:id`

```JSON
    {
        id,
        tag_name,
        products:[
            {
                id,
                product_name,
                price,
                stock,
                category_id,
                product_tag :{
                    id,
                    product_id,
                    tag_id
                }
            },
            ...
        ]

    }
```

- Create new category: post `/tags`
- Update category by id: put `/tags/:id`
- Delete category by id: delete `/tags/:id`

## Contribution

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License

MIT License ![MIT](https://img.shields.io/github/license/hmhtom/e-commerce-backend?style=plastic)

Copyright (c) 2022 hmhtom

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
