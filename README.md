# **Product Review System – MongoDB Schema (Mongoose)**

A well-structured **Mongoose schema** designed for a scalable **Product Review Platform**.  
This project models products and the reviews they receive, implementing strong validation, referencing, and clean schema design practices.

---

## **Overview**

The project defines two core Mongoose models — **Product** and **Review** — connected through referencing for a one-to-many relationship.  
It ensures data consistency, input validation, and production-ready design with trimmed strings, enums, and default values.

---

## **Features**

- **Clean Data Modeling:** Organized schemas for `Product` and `Review`
- **Strong Validation:** Uses `required`, `enum`, `min`, and `max` for safe data entry
- **Referencing:** Connects reviews with their corresponding products
- **Defaults & Timestamps:** Automatically handles common field values
- **Scalability:** Ready for integration into a full-stack product review application

---

## **Schema Summary**

### **Product Schema**
| Field | Type | Description |
|--------|------|-------------|
| `name` | String | Product name *(required)* |
| `category` | String | Category of product; enum: `electronics`, `fashion`, `home`, `books` |
| `price` | Number | Price in INR *(min: 1, required)* |
| `inStock` | Boolean | Product availability *(default: true)* |
| `releaseDate` | Date | Optional launch date |
| `reviews` | [ObjectId] | References to Review documents |

### **Review Schema**
| Field | Type | Description |
|--------|------|-------------|
| `reviewerName` | String | Name of reviewer *(required)* |
| `rating` | Number | Rating between 1–5 *(required)* |
| `comment` | String | Optional review text |
| `createdAt` | Date | Default: current date |
| `product` | ObjectId | Reference to the related Product *(required)* |

---

## **Example Document**

```json
{
  "name": "Wireless Earbuds",
  "category": "electronics",
  "price": 2999,
  "inStock": true,
  "reviews": [
    {
      "reviewerName": "Jane Doe",
      "rating": 5,
      "comment": "Excellent sound quality!"
    }
  ]
}
