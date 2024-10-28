```java
package com.sunilos.dto;

import javax.persistence.Column;
import javax.persistence.Entity;
import javax.persistence.Table;

/**
 * RoleDTO class is a persistent object that represents the roles of users. 
 * It is mapped to the "ST_ROLE" table in the database.
 * 
 * @author SunilOS
 * @version 1.0
 * @Copyright (c) SunilOS
 */
@Entity
@Table(name = "ST_ROLE")
public class RoleDTO extends BaseDTO {

    /**
     * Constant representing the Administrator role.
     */
    public static final int ADMIN = 1;

    /**
     * Constant representing the Student role.
     */
    public static final int STUDENT = 2;

    /**
     * Constant representing the College role.
     */
    public static final int COLLEGE = 3;

    /**
     * The name of the role, limited to a maximum of 50 characters.
     */
    @Column(name = "NAME", length = 50)
    private String name;

    /**
     * The description of the role, limited to a maximum of 255 characters.
     */
    @Column(name = "DESCRIPTION", length = 255)
    private String description;

    /**
     * Gets the name of the role.
     * 
     * @return name (as String)
     */
    public String getName() {
        return name;
    }

    /**
     * Sets the name of the role.
     * 
     * @param name the name to set for the role
     */
    public void setName(String name) {
        this.name = name;
    }

    /**
     * Gets the description of the role.
     * 
     * @return description (as String)
     */
    public String getDescription() {
        return description;
    }

    /**
     * Sets the description of the role.
     * 
     * @param description the description to set for the role
     */
    public void setDescription(String description) {
        this.description = description;
    }

    /**
     * Implementation of the getKey() method inherited from BaseDTO, 
     * which displays the unique identifier for the role.
     * 
     * @return id (as String)
     */
    @Override
    public String getKey() {
        return String.valueOf(id);
    }

    /**
     * Implementation of the getValue() method inherited from BaseDTO, 
     * which displays the name of the role.
     * 
     * @return name (as String)
     */
    @Override
    public String getValue() {
        return name;
    }
}
```

### Code Explanation

- **RoleDTO Class**: This class represents the roles of users. It is mapped to the "ST_ROLE" database table and stores information about various user roles.

- **Constants**: The constants `ADMIN`, `STUDENT`, and `COLLEGE` represent specific roles. These constants help in identifying roles in other parts of the class.

- **Fields**:
  - `name`: This is the name of the role, which can be a maximum of 50 characters long.
  - `description`: This is the description of the role, which can be a maximum of 255 characters long.

- **Getters and Setters**: The methods `getName()`, `setName()`, `getDescription()`, and `setDescription()` allow for getting and setting the name and description.

- **getKey() and getValue() Methods**: These methods are inherited from the `BaseDTO` class. The `getKey()` method returns the unique identifier for the role, while the `getValue()` method returns the name of the role. These methods are helpful for displaying user roles in a dropdown list.
