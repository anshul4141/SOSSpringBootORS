```java
package com.sunilos.dto;

import java.util.Date;
import javax.persistence.Column;
import javax.persistence.Entity;
import javax.persistence.Table;

/**
 * StudentDTO class represents a student entity in the system.
 * It is a persistent object mapped to the "ST_STUDENT" table in the database.
 * 
 * @author SunilOS
 * @version 1.0
 * @Copyright (c) SunilOS
 */
@Entity
@Table(name = "ST_STUDENT")
public class StudentDTO extends BaseDTO {
    /**
     * The first name of the student.
     */
    @Column(name = "FIRSTNAME", length = 50)
    private String firstName;

    /**
     * The last name of the student.
     */
    @Column(name = "LASTNAME", length = 50)
    private String lastName;

    /**
     * The date of birth of the student.
     */
    @Column(name = "DOB")
    private Date dob;

    /**
     * The mobile number of the student.
     */
    @Column(name = "MOBILENO", length = 15)
    private String mobileNo;

    /**
     * The email address of the student.
     */
    @Column(name = "EMAIL", length = 50)
    private String email;

    /**
     * The college ID associated with the student.
     */
    @Column(name = "COLLEGEID")
    private Long collegeId;

    /**
     * The name of the college the student is enrolled in.
     */
    @Column(name = "COLLEGENAME", length = 50)
    private String collegeName;

    /**
     * Gets the first name of the student.
     * 
     * @return firstName (as String)
     */
    public String getFirstName() {
        return firstName;
    }

    /**
     * Sets the first name of the student.
     * 
     * @param firstName the first name to set for the student
     */
    public void setFirstName(String firstName) {
        this.firstName = firstName;
    }

    /**
     * Gets the last name of the student.
     * 
     * @return lastName (as String)
     */
    public String getLastName() {
        return lastName;
    }

    /**
     * Sets the last name of the student.
     * 
     * @param lastName the last name to set for the student
     */
    public void setLastName(String lastName) {
        this.lastName = lastName;
    }

    /**
     * Gets the date of birth of the student.
     * 
     * @return dob (as Date)
     */
    public Date getDob() {
        return dob;
    }

    /**
     * Sets the date of birth of the student.
     * 
     * @param dob the date of birth to set for the student
     */
    public void setDob(Date dob) {
        this.dob = dob;
    }

    /**
     * Gets the mobile number of the student.
     * 
     * @return mobileNo (as String)
     */
    public String getMobileNo() {
        return mobileNo;
    }

    /**
     * Sets the mobile number of the student.
     * 
     * @param mobileNo the mobile number to set for the student
     */
    public void setMobileNo(String mobileNo) {
        this.mobileNo = mobileNo;
    }

    /**
     * Gets the email address of the student.
     * 
     * @return email (as String)
     */
    public String getEmail() {
        return email;
    }

    /**
     * Sets the email address of the student.
     * 
     * @param email the email address to set for the student
     */
    public void setEmail(String email) {
        this.email = email;
    }

    /**
     * Gets the college ID associated with the student.
     * 
     * @return collegeId (as Long)
     */
    public Long getCollegeId() {
        return collegeId;
    }

    /**
     * Sets the college ID for the student.
     * 
     * @param collegeId the college ID to set for the student
     */
    public void setCollegeId(Long collegeId) {
        this.collegeId = collegeId;
    }

    /**
     * Gets the college name the student is enrolled in.
     * 
     * @return collegeName (as String)
     */
    public String getCollegeName() {
        return collegeName;
    }

    /**
     * Sets the college name for the student.
     * 
     * @param collegeName the college name to set for the student
     */
    public void setCollegeName(String collegeName) {
        this.collegeName = collegeName;
    }

    /**
     * Returns the unique key (ID) of the student as a String.
     * 
     * @return id (as String)
     */
    public String getKey() {
        return id + "";
    }

    /**
     * Returns the value representation of the student, which is 
     * the concatenation of the first name and last name.
     * 
     * @return full name (as String)
     */
    public String getValue() {
        return firstName + " " + lastName;
    }
}
```

### Code Explanation

- **StudentDTO Class**: This class represents a student entity in the application. It maps to the "ST_STUDENT" table in the database and stores information about students.

- **Fields**:
  - `firstName`: The student's first name, with a maximum length of 50 characters.
  - `lastName`: The student's last name, also with a maximum length of 50 characters.
  - `dob`: The date of birth of the student.
  - `mobileNo`: The student's mobile number, limited to 15 characters.
  - `email`: The student's email address, with a maximum length of 50 characters.
  - `collegeId`: The ID of the college the student is associated with.
  - `collegeName`: The name of the college the student is enrolled in, limited to 50 characters.

- **Getters and Setters**: The methods provide access to the private fields, allowing other classes to retrieve and update the values.

- **getKey() and getValue() Methods**: 
  - `getKey()`: Returns the unique identifier for the student as a string.
  - `getValue()`: Returns a string representation of the student's full name, concatenating the first and last names.
