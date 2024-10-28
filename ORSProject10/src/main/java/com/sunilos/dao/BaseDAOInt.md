```java
package com.sunilos.dao;

import java.util.List;

/**
 * Role DAO (Data Access Object) interface for performing CRUD operations.
 * 
 * @param <T> the type of the DTO (Data Transfer Object) that this DAO handles
 * @author SunilOS
 * @version 1.0
 * @Copyright (c) SunilOS
 */
public interface BaseDAOInt<T> {

    /**
     * Adds a new record.
     * 
     * @param dto the DTO object to be added
     * @return the generated primary key of the added record
     */
    public long add(T dto);

    /**
     * Updates an existing record.
     * 
     * @param dto the DTO object with updated data
     */
    public void update(T dto);

    /**
     * Deletes an existing record.
     * 
     * @param dto the DTO object to be deleted
     */
    public void delete(T dto);

    /**
     * Finds a record by its primary key.
     * 
     * @param pk the primary key of the record to be found
     * @return the DTO object found, or null if not found
     */
    public T findByPK(long pk);

    /**
     * Searches for records with pagination support.
     * 
     * @param dto the DTO object with search criteria
     * @param pageNo the page number to retrieve
     * @param pageSize the number of records per page
     * @return a list of DTO objects matching the search criteria
     */
    public List<T> search(T dto, int pageNo, int pageSize);

    /**
     * Searches for records without pagination.
     * 
     * @param dto the DTO object with search criteria
     * @return a list of DTO objects matching the search criteria
     */
    public List<T> search(T dto);
}
```

### Explanation

1. **Interface Overview**:
   - The `BaseDAOInt` interface defines the standard Data Access Object (DAO) operations that can be performed on various types of DTOs. It uses generics (`<T>`) to allow flexibility in handling different types of data transfer objects.

2. **Generic Parameter**:
   - **`<T>`**: This is a type parameter that allows the interface to operate on any DTO type. This means you can implement this interface for specific DTOs like `RoleDTO`, `StudentDTO`, etc.

3. **CRUD Operations**:
   - **`add(T dto)`**: This method is responsible for adding a new record to the database. It returns the generated primary key of the newly created record, which can be useful for further operations or confirmations.
   - **`update(T dto)`**: This method updates an existing record in the database using the provided DTO object, which contains the updated data.
   - **`delete(T dto)`**: This method deletes a record based on the provided DTO object. Typically, the DTO would include the primary key or some identifying information.
   - **`findByPK(long pk)`**: This method retrieves a record by its primary key. If a matching record is found, it returns the corresponding DTO object; otherwise, it returns null.

4. **Search Operations**:
   - **`search(T dto, int pageNo, int pageSize)`**: This method allows searching for records based on certain criteria specified in the DTO. It supports pagination, allowing you to retrieve a specific page of results based on the `pageNo` and `pageSize` parameters.
   - **`search(T dto)`**: This method performs a search for records without pagination. It returns all records that match the criteria specified in the DTO.

5. **Use Cases**:
   - This interface is typically implemented by concrete DAO classes for different entities, such as `RoleDAO`, `StudentDAO`, etc. It provides a consistent API for performing data operations, making it easier to manage different types of data while following the DRY (Don't Repeat Yourself) principle.

6. **Advantages**:
   - **Code Reusability**: By using generics, the same interface can be reused for various entities without duplication of code.
   - **Maintainability**: Changes to the DAO operations can be made in one place (the interface), and all implementing classes will automatically inherit those changes.
   - **Flexibility**: Developers can easily implement this interface for any DTO type, which promotes a clean and organized architecture in the application.
