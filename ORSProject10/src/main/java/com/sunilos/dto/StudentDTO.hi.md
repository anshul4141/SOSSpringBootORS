```java
package com.sunilos.dto;

import java.util.Date;
import javax.persistence.Column;
import javax.persistence.Entity;
import javax.persistence.Table;

/**
 * StudentDTO क्लास एक छात्र की इकाई का प्रतिनिधित्व करती है।
 * यह डेटाबेस में "ST_STUDENT" तालिका के लिए एक स्थायी ऑब्जेक्ट है।
 * 
 * @author SunilOS
 * @version 1.0
 * @Copyright (c) SunilOS
 */
@Entity
@Table(name = "ST_STUDENT")
public class StudentDTO extends BaseDTO {
    /**
     * छात्र का पहला नाम।
     */
    @Column(name = "FIRSTNAME", length = 50)
    private String firstName;

    /**
     * छात्र का अंतिम नाम।
     */
    @Column(name = "LASTNAME", length = 50)
    private String lastName;

    /**
     * छात्र की जन्मतिथि।
     */
    @Column(name = "DOB")
    private Date dob;

    /**
     * छात्र का मोबाइल नंबर।
     */
    @Column(name = "MOBILENO", length = 15)
    private String mobileNo;

    /**
     * छात्र का ईमेल पता।
     */
    @Column(name = "EMAIL", length = 50)
    private String email;

    /**
     * छात्र से संबंधित कॉलेज आईडी।
     */
    @Column(name = "COLLEGEID")
    private Long collegeId;

    /**
     * छात्र के नामांकित कॉलेज का नाम।
     */
    @Column(name = "COLLEGENAME", length = 50)
    private String collegeName;

    /**
     * एक्सेसर
     */

    /**
     * छात्र का पहला नाम प्राप्त करें।
     * 
     * @return पहला नाम (String के रूप में)
     */
    public String getFirstName() {
        return firstName;
    }

    /**
     * छात्र का पहला नाम सेट करें।
     * 
     * @param firstName छात्र के लिए सेट करने के लिए पहला नाम
     */
    public void setFirstName(String firstName) {
        this.firstName = firstName;
    }

    /**
     * छात्र का अंतिम नाम प्राप्त करें।
     * 
     * @return अंतिम नाम (String के रूप में)
     */
    public String getLastName() {
        return lastName;
    }

    /**
     * छात्र का अंतिम नाम सेट करें।
     * 
     * @param lastName छात्र के लिए सेट करने के लिए अंतिम नाम
     */
    public void setLastName(String lastName) {
        this.lastName = lastName;
    }

    /**
     * छात्र की जन्मतिथि प्राप्त करें।
     * 
     * @return जन्मतिथि (Date के रूप में)
     */
    public Date getDob() {
        return dob;
    }

    /**
     * छात्र की जन्मतिथि सेट करें।
     * 
     * @param dob छात्र के लिए सेट करने के लिए जन्मतिथि
     */
    public void setDob(Date dob) {
        this.dob = dob;
    }

    /**
     * छात्र का मोबाइल नंबर प्राप्त करें।
     * 
     * @return मोबाइल नंबर (String के रूप में)
     */
    public String getMobileNo() {
        return mobileNo;
    }

    /**
     * छात्र का मोबाइल नंबर सेट करें।
     * 
     * @param mobileNo छात्र के लिए सेट करने के लिए मोबाइल नंबर
     */
    public void setMobileNo(String mobileNo) {
        this.mobileNo = mobileNo;
    }

    /**
     * छात्र का ईमेल पता प्राप्त करें।
     * 
     * @return ईमेल (String के रूप में)
     */
    public String getEmail() {
        return email;
    }

    /**
     * छात्र का ईमेल पता सेट करें।
     * 
     * @param email छात्र के लिए सेट करने के लिए ईमेल पता
     */
    public void setEmail(String email) {
        this.email = email;
    }

    /**
     * छात्र के साथ संबंधित कॉलेज आईडी प्राप्त करें।
     * 
     * @return कॉलेज आईडी (Long के रूप में)
     */
    public Long getCollegeId() {
        return collegeId;
    }

    /**
     * छात्र के लिए कॉलेज आईडी सेट करें।
     * 
     * @param collegeId छात्र के लिए सेट करने के लिए कॉलेज आईडी
     */
    public void setCollegeId(Long collegeId) {
        this.collegeId = collegeId;
    }

    /**
     * छात्र के नामांकित कॉलेज का नाम प्राप्त करें।
     * 
     * @return कॉलेज का नाम (String के रूप में)
     */
    public String getCollegeName() {
        return collegeName;
    }

    /**
     * छात्र के लिए कॉलेज का नाम सेट करें।
     * 
     * @param collegeName छात्र के लिए सेट करने के लिए कॉलेज का नाम
     */
    public void setCollegeName(String collegeName) {
        this.collegeName = collegeName;
    }

    /**
     * छात्र का अद्वितीय कुंजी (आईडी) स्ट्रिंग के रूप में लौटाता है।
     * 
     * @return आईडी (String के रूप में)
     */
    public String getKey() {
        return id + "";
    }

    /**
     * छात्र का मूल्य प्रतिनिधित्व लौटाता है, जो 
     * पहले और अंतिम नाम का संयोजन है।
     * 
     * @return पूरा नाम (String के रूप में)
     */
    public String getValue() {
        return firstName + " " + lastName;
    }
}
```

### कोड व्याख्या

- **StudentDTO क्लास**: यह क्लास एक छात्र की इकाई का प्रतिनिधित्व करती है। यह "ST_STUDENT" तालिका के लिए मैप की जाती है और छात्रों के बारे में जानकारी संग्रहीत करती है।

- **फील्ड्स**:
  - `firstName`: छात्र का पहला नाम, अधिकतम 50 अक्षरों की लंबाई के साथ।
  - `lastName`: छात्र का अंतिम नाम, अधिकतम 50 अक्षरों की लंबाई के साथ।
  - `dob`: छात्र की जन्मतिथि।
  - `mobileNo`: छात्र का मोबाइल नंबर, 15 अक्षरों तक सीमित।
  - `email`: छात्र का ईमेल पता, अधिकतम 50 अक्षरों की लंबाई के साथ।
  - `collegeId`: छात्र से संबंधित कॉलेज की आईडी।
  - `collegeName`: छात्र के नामांकित कॉलेज का नाम, 50 अक्षरों तक सीमित।

- **गेटर्स और सेटर्स**: ये विधियाँ निजी फ़ील्ड्स तक पहुँच प्रदान करती हैं, जिससे अन्य कक्षाएँ मानों को प्राप्त और अपडेट कर सकती हैं।

- **getKey() और getValue() विधियाँ**: 
  - `getKey()`: छात्र की अद्वितीय पहचान (आईडी) को स्ट्रिंग के रूप में लौटाता है।
  - `getValue()`: छात्र के पूर्ण नाम का स्ट्रिंग प्रतिनिधित्व लौटाता है, जिसमें पहले और अंतिम नामों का संयोजन होता है।
