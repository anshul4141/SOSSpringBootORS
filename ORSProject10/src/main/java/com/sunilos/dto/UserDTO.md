```java
package com.sunilos.dto;

import java.sql.Date;
import java.sql.Timestamp;
import javax.persistence.Column;
import javax.persistence.Entity;
import javax.persistence.Table;

/**
 * The UserDTO class is a Data Transfer Object (DTO) that represents a User entity.
 * It maps to the "ST_USER" table in the database and holds user-related data.
 * 
 * UserDTO extends BaseDTO, providing ID and common properties, 
 * and implements DropdownList to return user information for display in dropdowns.
 * 
 * This class uses Hibernate annotations for ORM (Object-Relational Mapping).
 * 
 * @author SunilOS
 * @version 1.0
 */
@Entity
@Table(name = "ST_USER")
public class UserDTO extends BaseDTO implements DropdownList {

    /**
     * Constant representing an active user status.
     */
    public static final String ACTIVE = "Active";
    
    /**
     * Constant representing an inactive user status.
     */
    public static final String INACTIVE = "Inactive";
    
    /**
     * User's first name. Limited to 50 characters in length.
     */
    @Column(name = "FIRST_NAME", length = 50)
    private String firstName;
    
    /**
     * User's last name. Limited to 50 characters in length.
     */
    @Column(name = "LAST_NAME", length = 50)
    private String lastName;
    
    /**
     * User's login username. Limited to 50 characters in length.
     */
    @Column(name = "LOGIN", length = 50)
    private String login;
    
    /**
     * User's password. Limited to 50 characters in length.
     */
    @Column(name = "PASSWORD", length = 50)
    private String password;
    
    /**
     * User's date of birth.
     */
    @Column(name = "DOB")
    private Date dob;
    
    /**
     * User's mobile number. Limited to 15 characters in length.
     */
    @Column(name = "MOBILE_NO", length = 15)
    private String mobileNo;
    
    /**
     * Role ID associated with the user, representing the user's role.
     */
    @Column(name = "ROLE_ID")
    private long roleId;
    
    /**
     * Count of unsuccessful login attempts by the user.
     */
    @Column(name = "UNSUCCESSFUL_LOGIN")
    private int unSuccessfulLogin;
    
    /**
     * User's gender, limited to 10 characters in length.
     */
    @Column(name = "GENDER", length = 10)
    private String gender;
    
    /**
     * Timestamp of the user's last login.
     */
    @Column(name = "LAST_LOGIN", length = 50)
    private Timestamp lastLogin;
    
    /**
     * Lock status of the user account, defaulting to inactive.
     */
    @Column(name = "USER_LOCK", length = 10)
    private String lock = INACTIVE;
    
    /**
     * IP address from which the user registered.
     */
    @Column(name = "REGISTERED_IP", length = 20)
    private String registeredIP;
    
    /**
     * IP address used during the user's last login.
     */
    @Column(name = "LAST_LOGIN_IP", length = 20)
    private String lastLoginIP;

    // Getters and Setters for each field

    /**
     * Retrieves the user's first name.
     * 
     * @return firstName as String
     */
    public String getFirstName() {
        return firstName;
    }

    /**
     * Sets the user's first name.
     * 
     * @param firstName User's first name to set
     */
    public void setFirstName(String firstName) {
        this.firstName = firstName;
    }

    /**
     * Retrieves the user's last name.
     * 
     * @return lastName as String
     */
    public String getLastName() {
        return lastName;
    }

    /**
     * Sets the user's last name.
     * 
     * @param lastName User's last name to set
     */
    public void setLastName(String lastName) {
        this.lastName = lastName;
    }

    /**
     * Retrieves the user's login username.
     * 
     * @return login as String
     */
    public String getLogin() {
        return login;
    }

    /**
     * Sets the user's login username.
     * 
     * @param login User's login name to set
     */
    public void setLogin(String login) {
        this.login = login;
    }

    /**
     * Retrieves the user's password.
     * 
     * @return password as String
     */
    public String getPassword() {
        return password;
    }

    /**
     * Sets the user's password.
     * 
     * @param password User's password to set
     */
    public void setPassword(String password) {
        this.password = password;
    }

    /**
     * Retrieves the user's date of birth.
     * 
     * @return dob as Date
     */
    public Date getDob() {
        return dob;
    }

    /**
     * Sets the user's date of birth.
     * 
     * @param dob User's date of birth to set
     */
    public void setDob(Date dob) {
        this.dob = dob;
    }

    /**
     * Retrieves the user's role ID.
     * 
     * @return roleId as long
     */
    public long getRoleId() {
        return roleId;
    }

    /**
     * Sets the user's role ID.
     * 
     * @param roleId Role ID to set for the user
     */
    public void setRoleId(long roleId) {
        this.roleId = roleId;
    }

    /**
     * Retrieves the count of unsuccessful login attempts by the user.
     * 
     * @return unSuccessfulLogin as int
     */
    public int getUnSuccessfulLogin() {
        return unSuccessfulLogin;
    }

    /**
     * Sets the count of unsuccessful login attempts for the user.
     * 
     * @param unSuccessfulLogin Count to set
     */
    public void setUnSuccessfulLogin(int unSuccessfulLogin) {
        this.unSuccessfulLogin = unSuccessfulLogin;
    }

    /**
     * Retrieves the user's mobile number.
     * 
     * @return mobileNo as String
     */
    public String getMobileNo() {
        return mobileNo;
    }

    /**
     * Sets the user's mobile number.
     * 
     * @param mobileNo Mobile number to set
     */
    public void setMobileNo(String mobileNo) {
        this.mobileNo = mobileNo;
    }

    /**
     * Retrieves the user's gender.
     * 
     * @return gender as String
     */
    public String getGender() {
        return gender;
    }

    /**
     * Sets the user's gender.
     * 
     * @param gender Gender to set for the user
     */
    public void setGender(String gender) {
        this.gender = gender;
    }

    /**
     * Retrieves the timestamp of the user's last login.
     * 
     * @return lastLogin as Timestamp
     */
    public Timestamp getLastLogin() {
        return lastLogin;
    }

    /**
     * Sets the timestamp of the user's last login.
     * 
     * @param lastLogin Last login timestamp to set
     */
    public void setLastLogin(Timestamp lastLogin) {
        this.lastLogin = lastLogin;
    }

    /**
     * Retrieves the lock status of the user.
     * 
     * @return lock as String
     */
    public String getLock() {
        return lock;
    }

    /**
     * Sets the lock status for the user.
     * 
     * @param lock Lock status to set
     */
    public void setLock(String lock) {
        this.lock = lock;
    }

    /**
     * Retrieves the IP address from which the user registered.
     * 
     * @return registeredIP as String
     */
    public String getRegisteredIP() {
        return registeredIP;
    }

    /**
     * Sets the IP address from which the user registered.
     * 
     * @param registeredIP Registered IP address to set
     */
    public void setRegisteredIP(String registeredIP) {
        this.registeredIP = registeredIP;
    }

    /**
     * Retrieves the IP address of the user's last login.
     * 
     * @return lastLoginIP as String
     */
    public String getLastLoginIP() {
        return lastLoginIP;
    }

    /**
     * Sets the IP address of the user's last login.
     * 
     * @param lastLoginIP Last login IP address to set
     */
    public void setLastLoginIP(String lastLoginIP) {
        this.lastLoginIP = lastLoginIP;
    }

    /**
     * Retrieves the unique identifier of the user as a key.
     * 
     * @return String representation of user ID
     */
    public String getKey() {
        return id + "";
    }

    /**
     * Retrieves the user's display name, combining first and last names.
     * 
     * @return Concatenated firstName and lastName as display name
     */
    public String getValue() {
        return firstName + " " + lastName;
    }
}
```

### Explanation

- **Class-Level JavaDoc**: Explains the class purpose, relationships, and author details.
- **Fields**: Each field is mapped to a column in the `ST_USER` table, with annotations specifying column attributes.
- **Constants**: `ACTIVE` and `INACTIVE` constants represent possible lock states for the user.
- **Getters and Setters**: Provide access to each

 field with relevant comments describing each field's purpose.
- **`getKey` and `getValue` Methods**: Implementations from `DropdownList` interface that provide unique identifiers and display names for dropdown lists.
