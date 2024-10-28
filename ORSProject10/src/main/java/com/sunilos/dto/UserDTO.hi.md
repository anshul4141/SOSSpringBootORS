```java
package com.sunilos.dto;

import java.sql.Date;
import java.sql.Timestamp;
import javax.persistence.Column;
import javax.persistence.Entity;
import javax.persistence.Table;

/**
 * UserDTO कक्षा एक डेटा ट्रांसफर ऑब्जेक्ट (DTO) है जो एक उपयोगकर्ता इकाई का प्रतिनिधित्व करती है।
 * यह डेटाबेस में "ST_USER" तालिका के साथ मैप होती है और उपयोगकर्ता से संबंधित डेटा रखती है।
 * 
 * UserDTO BaseDTO को विस्तारित करता है, जो ID और सामान्य गुण प्रदान करता है,
 * और DropdownList को लागू करता है ताकि ड्रॉपडाउन में उपयोगकर्ता जानकारी प्रदर्शित हो सके।
 * 
 * इस कक्षा में ORM (ऑब्जेक्ट-रिलेशनल मैपिंग) के लिए हाइबरनेट एनोटेशन का उपयोग किया गया है।
 * 
 * लेखक: SunilOS
 * संस्करण: 1.0
 */
@Entity
@Table(name = "ST_USER")
public class UserDTO extends BaseDTO implements DropdownList {

    /**
     * सक्रिय उपयोगकर्ता स्थिति का प्रतिनिधित्व करने वाला स्थिरांक।
     */
    public static final String ACTIVE = "Active";
    
    /**
     * निष्क्रिय उपयोगकर्ता स्थिति का प्रतिनिधित्व करने वाला स्थिरांक।
     */
    public static final String INACTIVE = "Inactive";
    
    /**
     * उपयोगकर्ता का पहला नाम। अधिकतम 50 वर्णों तक सीमित।
     */
    @Column(name = "FIRST_NAME", length = 50)
    private String firstName;
    
    /**
     * उपयोगकर्ता का अंतिम नाम। अधिकतम 50 वर्णों तक सीमित।
     */
    @Column(name = "LAST_NAME", length = 50)
    private String lastName;
    
    /**
     * उपयोगकर्ता का लॉगिन नाम। अधिकतम 50 वर्णों तक सीमित।
     */
    @Column(name = "LOGIN", length = 50)
    private String login;
    
    /**
     * उपयोगकर्ता का पासवर्ड। अधिकतम 50 वर्णों तक सीमित।
     */
    @Column(name = "PASSWORD", length = 50)
    private String password;
    
    /**
     * उपयोगकर्ता की जन्म तिथि।
     */
    @Column(name = "DOB")
    private Date dob;
    
    /**
     * उपयोगकर्ता का मोबाइल नंबर। अधिकतम 15 वर्णों तक सीमित।
     */
    @Column(name = "MOBILE_NO", length = 15)
    private String mobileNo;
    
    /**
     * उपयोगकर्ता की भूमिका से संबंधित भूमिका आईडी।
     */
    @Column(name = "ROLE_ID")
    private long roleId;
    
    /**
     * उपयोगकर्ता के असफल लॉगिन प्रयासों की गिनती।
     */
    @Column(name = "UNSUCCESSFUL_LOGIN")
    private int unSuccessfulLogin;
    
    /**
     * उपयोगकर्ता का लिंग, अधिकतम 10 वर्णों तक सीमित।
     */
    @Column(name = "GENDER", length = 10)
    private String gender;
    
    /**
     * उपयोगकर्ता के अंतिम लॉगिन का समय।
     */
    @Column(name = "LAST_LOGIN", length = 50)
    private Timestamp lastLogin;
    
    /**
     * उपयोगकर्ता खाता का लॉक स्थिति, जो डिफ़ॉल्ट रूप से निष्क्रिय होती है।
     */
    @Column(name = "USER_LOCK", length = 10)
    private String lock = INACTIVE;
    
    /**
     * आईपी पता जिससे उपयोगकर्ता ने पंजीकरण किया था।
     */
    @Column(name = "REGISTERED_IP", length = 20)
    private String registeredIP;
    
    /**
     * उपयोगकर्ता के अंतिम लॉगिन का आईपी पता।
     */
    @Column(name = "LAST_LOGIN_IP", length = 20)
    private String lastLoginIP;

    // प्रत्येक फ़ील्ड के लिए गेटर्स और सेटर्स

    /**
     * उपयोगकर्ता का पहला नाम प्राप्त करता है।
     * 
     * @return firstName (String में)
     */
    public String getFirstName() {
        return firstName;
    }

    /**
     * उपयोगकर्ता का पहला नाम सेट करता है।
     * 
     * @param firstName उपयोगकर्ता का पहला नाम सेट करने के लिए
     */
    public void setFirstName(String firstName) {
        this.firstName = firstName;
    }

    /**
     * उपयोगकर्ता का अंतिम नाम प्राप्त करता है।
     * 
     * @return lastName (String में)
     */
    public String getLastName() {
        return lastName;
    }

    /**
     * उपयोगकर्ता का अंतिम नाम सेट करता है।
     * 
     * @param lastName उपयोगकर्ता का अंतिम नाम सेट करने के लिए
     */
    public void setLastName(String lastName) {
        this.lastName = lastName;
    }

    /**
     * उपयोगकर्ता का लॉगिन नाम प्राप्त करता है।
     * 
     * @return login (String में)
     */
    public String getLogin() {
        return login;
    }

    /**
     * उपयोगकर्ता का लॉगिन नाम सेट करता है।
     * 
     * @param login उपयोगकर्ता का लॉगिन नाम सेट करने के लिए
     */
    public void setLogin(String login) {
        this.login = login;
    }

    /**
     * उपयोगकर्ता का पासवर्ड प्राप्त करता है।
     * 
     * @return password (String में)
     */
    public String getPassword() {
        return password;
    }

    /**
     * उपयोगकर्ता का पासवर्ड सेट करता है।
     * 
     * @param password उपयोगकर्ता का पासवर्ड सेट करने के लिए
     */
    public void setPassword(String password) {
        this.password = password;
    }

    /**
     * उपयोगकर्ता की जन्म तिथि प्राप्त करता है।
     * 
     * @return dob (Date में)
     */
    public Date getDob() {
        return dob;
    }

    /**
     * उपयोगकर्ता की जन्म तिथि सेट करता है।
     * 
     * @param dob उपयोगकर्ता की जन्म तिथि सेट करने के लिए
     */
    public void setDob(Date dob) {
        this.dob = dob;
    }

    /**
     * उपयोगकर्ता की भूमिका आईडी प्राप्त करता है।
     * 
     * @return roleId (long में)
     */
    public long getRoleId() {
        return roleId;
    }

    /**
     * उपयोगकर्ता की भूमिका आईडी सेट करता है।
     * 
     * @param roleId उपयोगकर्ता की भूमिका आईडी सेट करने के लिए
     */
    public void setRoleId(long roleId) {
        this.roleId = roleId;
    }

    /**
     * असफल लॉगिन प्रयासों की गिनती प्राप्त करता है।
     * 
     * @return unSuccessfulLogin (int में)
     */
    public int getUnSuccessfulLogin() {
        return unSuccessfulLogin;
    }

    /**
     * असफल लॉगिन प्रयासों की गिनती सेट करता है।
     * 
     * @param unSuccessfulLogin गिनती सेट करने के लिए
     */
    public void setUnSuccessfulLogin(int unSuccessfulLogin) {
        this.unSuccessfulLogin = unSuccessfulLogin;
    }

    /**
     * उपयोगकर्ता का मोबाइल नंबर प्राप्त करता है।
     * 
     * @return mobileNo (String में)
     */
    public String getMobileNo() {
        return mobileNo;
    }

    /**
     * उपयोगकर्ता का मोबाइल नंबर सेट करता है।
     * 
     * @param mobileNo मोबाइल नंबर सेट करने के लिए
     */
    public void setMobileNo(String mobileNo) {
        this.mobileNo = mobileNo;
    }

    /**
     * उपयोगकर्ता का लिंग प्राप्त करता है।
     * 
     * @return gender (String में)
     */
    public String getGender() {
        return gender;
    }

    /**
     * उपयोगकर्ता का लिंग सेट करता है।
     * 
     * @param gender उपयोगकर्ता का लिंग सेट करने के लिए
     */
    public void setGender(String gender) {
        this.gender = gender;
    }

    /**
     * उपयोगकर्ता के अंतिम लॉगिन का समय प्राप्त करता है।
     * 
     * @return lastLogin (Timestamp में)
     */
    public Timestamp getLastLogin() {
        return lastLogin;
    }

    /**
     * उपयोगकर्ता के अंतिम लॉगिन का समय सेट करता है।
     * 
     * @param lastLogin अंतिम लॉगिन समय सेट करने के लिए
     */
    public void setLastLogin(Timestamp lastLogin) {
        this.lastLogin = lastLogin;
    }

    /**
     * उपयोगकर्ता का लॉक स्थिति प्राप्त करता है।
     * 
     * @return lock (String में)
     */
    public String getLock() {
        return lock;
    }

    /**
     * उपयोगकर्ता की लॉक स्थिति सेट करता है।
     * 
     * @param lock लॉक स्थिति सेट करने के लिए
     */
    public void setLock(String lock) {
        this.lock = lock;
    }

    /**
     * पंजीकरण के लिए उपयोगकर्ता का आईपी पता प्राप्त करता है।
     * 
     * @return registeredIP (String में)
     */
    public String getRegisteredIP() {
        return registeredIP;
    }

    /**
     * पंजीकरण के लिए उपयोगकर्ता का आईपी पता सेट करता है।
     * 
     * @param registeredIP पंजीकृत आईपी सेट करने के लिए
     */
    public void setRegisteredIP(String registeredIP) {
        this.registeredIP = registeredIP;
    }

    /**
     * उपयोगकर्ता के अंतिम लॉगिन का आईपी पता प्राप्त करता है।
     * 
     * @return lastLoginIP (String में)
     */
   

 public String getLastLoginIP() {
        return lastLoginIP;
    }

    /**
     * उपयोगकर्ता के अंतिम लॉगिन का आईपी पता सेट करता है।
     * 
     * @param lastLoginIP अंतिम लॉगिन आईपी सेट करने के लिए
     */
    public void setLastLoginIP(String lastLoginIP) {
        this.lastLoginIP = lastLoginIP;
    }

    /**
     * DropdownList इंटरफ़ेस का getKey() कार्यान्वयन, जो एक अद्वितीय कुंजी प्रदान करता है।
     * 
     * @return id (String में)
     */
    public String getKey() {
        return id + "";
    }

    /**
     * DropdownList इंटरफ़ेस का getValue() कार्यान्वयन, जो उपयोगकर्ता का नाम और उपनाम जोड़ता है।
     * 
     * @return fullName (String में)
     */
    public String getValue() {
        return firstName + " " + lastName;
    }
}
```

### कोड का व्याख्या

यह कोड `UserDTO` नामक एक कक्षा को परिभाषित करता है, जो उपयोगकर्ता के डेटा का एक डेटा ट्रांसफर ऑब्जेक्ट (DTO) है। यह कक्षा निम्नलिखित चीजों को समाहित करती है:

- **उपयोगकर्ता के डेटा के लिए विशेषताएँ**: जैसे कि पहला नाम, अंतिम नाम, लॉगिन, पासवर्ड, जन्म तिथि, मोबाइल नंबर, भूमिका आईडी, असफल लॉगिन प्रयासों की संख्या, लिंग, अंतिम लॉगिन समय, और आईपी पते।

- **गेटर्स और सेटर्स**: प्रत्येक विशेषता के लिए गेट और सेट विधियाँ हैं, जो डेटा को प्राप्त करने और सेट करने की अनुमति देती हैं।

- **की और मान प्राप्त करने के लिए विधियाँ**: `getKey()` और `getValue()` विधियाँ हैं, जो `DropdownList` इंटरफेस का हिस्सा हैं। ये ड्रॉपडाउन लिस्ट में उपयोगकर्ता की पहचान और नाम दिखाने के लिए उपयोग की जाती हैं।

- **प्रतिकृति और स्थिरांक**: इस कक्षा में उपयोगकर्ता की स्थिति को परिभाषित करने के लिए स्थिरांक (Constants) भी हैं, जैसे कि सक्रिय (Active) और निष्क्रिय (Inactive)।
