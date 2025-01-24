# Firestore Operations Documentation

This document outlines the Firestore operations performed by the application in the `firestore/src/app` directory.

## Collections

### restaurants

*   **Operations:**
    *   **READ**: `collectionData()` is used to read all documents from this collection.
    *   **READ**: `docData()` is used to read a specific document from this collection.
    * **READ**: `where()` is used to filter documents by `city`, `category` and `price`.
*   **Data Model:**

    ```typescript
    export interface Restaurant {
        id: string;
        avgRating: number;
        category: string;
        city: string;
        name: string;
        numRatings: number;
        photo: string;
        price: number;
    }
    ```

### ratings (subcollection)

*   **Operations:**
    *   **CREATE**: `addDoc()` is used to add a new rating document to this collection.
    *   **READ**: `collectionData()` is used to read all rating documents from this collection.
*   **Data Model:**

    ```typescript
    export interface Rating {
        id?: string;
        rating: number;
        text: string;
        timestamp?: Date;
        userId?: string;
        userName?: string;
    }
    ```

## Query Constraints
* **Operations**:
    * **READ**: `where()` is used to filter by city, category and price.
    * **READ**: `orderBy()` is used to order by `numRatings` or `avgRating`.

