# Product Finder 1.1 🎉

ProductFinderJS is made to simplify the integration of a complete product finder in your e-commerce projects

## Installation 🌍

    <script src="productFinder.js"></script>

## How it works ?

Initialize

```javascript
const SYSTEM = new ProductFinder(products);
// OR
const SYSTEM = new ProductFinder();
SYSTEM.loadProducts(products);
```

Schema of products

```javascript
const products = [
 "name": String,
 "properties": [String],
 "price": Number,
 "discount": Number|Boolean
];
```

You can add custom fields

---

## The ``setFilter`` function :

| Parameter | Type   | Required | Default |
| --------- | ------ | -------- | ------- |
| kind    | String | Yes       | No default       |
| value    | String | Number | Yes       | No default       |

---

### Define a discount filter

```javascript
// In percent (%)
SYSTEM.setFilter("discount", "50%");

// OR amount reduction
SYSTEM.setFilter("discount", 100);
```

---

### Define a price filter

```javascript
// The exact amount
SYSTEM.setFilter("price", 200);

// OR the min and max amount
SYSTEM.setFilter("price", "100:300");
```

---

### Define a property filter

```javascript
// The exact amount
SYSTEM.setFilter("property", "value");
```

---

## The ``removeFilter`` function :
Same as setFilter but to remove the filter

| Parameter | Type   | Required | Default |
| --------- | ------ | -------- | ------- |
| kind    | String | Yes       | No default       |
| value    | String | Number | Yes       | No default       |

---

## The ``hasFilter`` function :

```javascript
// The exact amount
SYSTEM.hasFilter("property", "value");
```

| Parameter | Type   | Required | Default |
| --------- | ------ | -------- | ------- |
| kind    | String | Yes       | No default       |
| value    | String | Number | Yes       | No default       |

---

## Reset filter :
```javascript
SYSTEM.resetFilters();
```

---

## Get function :
This function returns products with filters applied
```javascript
SYSTEM.get();
```

## Get Filters function :
This function returns the filters applied
```javascript
SYSTEM.getFilters();
```

---

# Product Finder DOM

ProductFinderJS DOM is an extension of the productFinderJS to simplify the integration of a product finder system with already created functions

## IMPORTANT
You must add productFinder.js before productFinderDOM, otherwise it will not work.  
And you can use the same functions on productFinderDOM and productFinder, it's just an extension no more, no less

## Installation 🌍
    <script src="productFinder.js"></script>
    <script src="productFinderDOM.js"></script>

## How it works ?

Initialize

```javascript
const SYSTEM = new ProductFinderDOM(products);
// OR
const SYSTEM = new ProductFinderDOM();
SYSTEM.loadProducts(products);
```

For the system to work properly you must give custom css class, attributes and launch a (js) function, oof

### HTML :
```html
    <button class="productfinder-dom" pf-dom-active="active" pf-dom-property="material_silver 925">Silver 925</button>
    <button class="productfinder-dom" pf-dom-active="active" pf-dom-property="material_silver 935">Silver 935</button>
    <button class="productfinder-dom" pf-dom-active="active" pf-dom-price="250">250€</button>
    <button class="productfinder-dom" pf-dom-active="active" pf-dom-price="250:500">250€</button>
    <button class="productfinder-dom" pf-dom-active="active" pf-dom-discount="50%">-50%</button>
```
*pf-dom-active attribute is the class which is added when the filter is activated, it is entirely optional

### JS :
elementFinder will find each element with the productfinder-dom class and attach a click listener to them
```javascript
SYSTEM.elementFinder();
```

### onChange
onChange is unique, you can only define one event
```javascript
function callback(){
    console.log(SYSTEM.get()); //example
}
SYSTEM.onChange(callback);
```