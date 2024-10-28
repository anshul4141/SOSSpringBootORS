```java
package com.sunilos.dto;

import javax.persistence.Column;
import javax.persistence.Entity;
import javax.persistence.Table;

/**
 * College Data Transfer Object (DTO) class that represents a college entity.
 * This class is used to transfer college data between different layers of the application.
 * 
 * @author SunilOS
 * @version 1.0
 * @Copyright (c) SunilOS
 */
@Entity
@Table(name = "ST_COLLEGE")
public class CollegeDTO extends BaseDTO {
    /**
     * Name of the college.
     */
    @Column(name = "NAME", length = 50)
    private String name;

    /**
     * Address of the college.
     */
    @Column(name = "ADDRESS", length = 50)
    private String address;

    /**
     * State where the college is located.
     */
    @Column(name = "STATE", length = 50)
    private String state;

    /**
     * City where the college is located.
     */
    @Column(name = "CITY", length = 50)
    private String city;

    /**
     * Phone number of the college.
     */
    @Column(name = "PHONENO", length = 15)
    private String phoneNo;

    /**
     * Returns the name of the college.
     * 
     * @return name of the college as a String.
     */
    public String getName() {
        return name;
    }

    /**
     * Sets the name of the college.
     * 
     * @param name the name to be set for the college.
     */
    public void setName(String name) {
        this.name = name;
    }

    /**
     * Returns the address of the college.
     * 
     * @return address of the college as a String.
     */
    public String getAddress() {
        return address;
    }

    /**
     * Sets the address of the college.
     * 
     * @param address the address to be set for the college.
     */
    public void setAddress(String address) {
        this.address = address;
    }

    /**
     * Returns the state of the college.
     * 
     * @return state of the college as a String.
     */
    public String getState() {
        return state;
    }

    /**
     * Sets the state of the college.
     * 
     * @param state the state to be set for the college.
     */
    public void setState(String state) {
        this.state = state;
    }

    /**
     * Returns the city of the college.
     * 
     * @return city of the college as a String.
     */
    public String getCity() {
        return city;
    }

    /**
     * Sets the city of the college.
     * 
     * @param city the city to be set for the college.
     */
    public void setCity(String city) {
        this.city = city;
    }

    /**
     * Returns the phone number of the college.
     * 
     * @return phone number of the college as a String.
     */
    public String getPhoneNo() {
        return phoneNo;
    }

    /**
     * Sets the phone number of the college.
     * 
     * @param phoneNo the phone number to be set for the college.
     */
    public void setPhoneNo(String phoneNo) {
        this.phoneNo = phoneNo;
    }

    /**
     * Returns a unique key for the college, which is the ID as a String.
     * 
     * @return ID of the college as a String.
     */
    public String getKey() {
        return id + "";
    }

    /**
     * Returns the display value for the college, which is its name.
     * 
     * @return name of the college as a String.
     */
    public String getValue() {
        return name;
    }
}
```

### Explanation

1. **Class Overview**:
   - **`CollegeDTO`**: This class represents a college entity and is used for transferring data related to colleges within the application. It extends `BaseDTO`, which presumably provides common properties and methods shared among various DTOs.

2. **Annotations**:
   - **`@Entity`**: Indicates that this class is a JPA entity and will be mapped to a database table.
   - **`@Table(name = "ST_COLLEGE")`**: Specifies the name of the database table (`ST_COLLEGE`) that this entity maps to.

3. **Attributes**:
   - Each attribute represents a column in the `ST_COLLEGE` table. The attributes are annotated with `@Column`, which specifies the column name and the length of the column in the database.
     - **`name`**: The name of the college.
     - **`address`**: The address where the college is located.
     - **`state`**: The state in which the college is situated.
     - **`city`**: The city where the college can be found.
     - **`phoneNo`**: The contact number for the college.

4. **Getters and Setters**:
   - Each attribute has a corresponding getter and setter method, allowing access to and modification of the attributes' values. This is a common practice in Java to follow encapsulation principles.

5. **Key and Value Methods**:
   - **`getKey()`**: Returns a unique identifier (ID) as a string, which can be useful when populating dropdown lists or for other identification purposes.
   - **`getValue()`**: Returns the name of the college, which is typically displayed in user interfaces.

### Usage
The `CollegeDTO` class can be used in various layers of an application, such as:
- **Data Access Layer**: To interact with the college database table.
- **Service Layer**: To transfer college data between different components of the application.
- **Presentation Layer**: To display college information in user interfaces, such as forms and tables.
