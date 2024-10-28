```java
package com.sunilos.dto;

/**
 * DropdownList interface is implemented by Data Transfer Objects (DTOs) 
 * that are used to create dropdown lists on HTML pages.
 * This interface defines the structure for objects that can be represented 
 * in dropdown menus, ensuring they provide a key-value pairing for 
 * display purposes.
 * 
 * @author SunilOS
 * @version 1.0
 * @Copyright (c) SunilOS
 */
public interface DropdownList {

    /**
     * Returns the key of the dropdown list element.
     * This key is typically used as the value for the option in the 
     * dropdown and is usually a unique identifier.
     * 
     * @return key as a String
     */
    public String getKey();

    /**
     * Returns the display text of the dropdown list element.
     * This text is what users see in the dropdown menu and represents
     * the corresponding value for the key.
     * 
     * @return value as a String
     */
    public String getValue();
}
```

### Explanation of the Code

- **Interface `DropdownList`**: 
  - This interface serves as a contract for any DTO (Data Transfer Object) that needs to be displayed in a dropdown list on HTML pages. By implementing this interface, classes ensure that they provide the necessary methods to generate dropdown options.

- **Methods**:
  - **`getKey()`**: 
    - This method is expected to return a unique identifier (key) for each dropdown list element. This key is often used in forms to submit the selected value.
    - **Return Type**: `String` - Represents the unique key for the dropdown option.
  
  - **`getValue()`**: 
    - This method returns the display text that will be shown to users in the dropdown. This text should be user-friendly and descriptive.
    - **Return Type**: `String` - Represents the display value for the dropdown option.

### Usage

- The `DropdownList` interface is useful in scenarios where you need to populate dropdown menus dynamically, such as when fetching a list of countries, roles, or other entities from a database. Classes implementing this interface can be easily iterated over to create HTML dropdowns, ensuring that both the key and the display value are accessible.
