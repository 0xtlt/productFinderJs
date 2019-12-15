# Product Finder 1.0 🎉

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