```java
package com.sunilos.dto;

import javax.persistence.Column;
import javax.persistence.Entity;
import javax.persistence.Table;

/**
 * RoleDTO कक्षा एक Persistent Object (स्थायी ऑब्जेक्ट) है, 
 * जो उपयोगकर्ता की भूमिकाओं को दर्शाती है। 
 * यह डेटाबेस में "ST_ROLE" तालिका के साथ मैप होती है।
 * 
 * @author SunilOS
 * @version 1.0
 * @Copyright (c) SunilOS
 */
@Entity
@Table(name = "ST_ROLE")
public class RoleDTO extends BaseDTO {

    /**
     * Administrator की भूमिका को दर्शाने वाला स्थिरांक।
     */
    public static final int ADMIN = 1;

    /**
     * Student की भूमिका को दर्शाने वाला स्थिरांक।
     */
    public static final int STUDENT = 2;

    /**
     * College की भूमिका को दर्शाने वाला स्थिरांक।
     */
    public static final int COLLEGE = 3;

    /**
     * भूमिका का नाम। अधिकतम 50 वर्णों तक सीमित।
     */
    @Column(name = "NAME", length = 50)
    private String name;

    /**
     * भूमिका का विवरण। अधिकतम 255 वर्णों तक सीमित।
     */
    @Column(name = "DESCRIPTION", length = 255)
    private String description;

    /**
     * भूमिका का नाम प्राप्त करता है।
     * 
     * @return नाम (String में)
     */
    public String getName() {
        return name;
    }

    /**
     * भूमिका का नाम सेट करता है।
     * 
     * @param name भूमिका का नाम सेट करने के लिए
     */
    public void setName(String name) {
        this.name = name;
    }

    /**
     * भूमिका का विवरण प्राप्त करता है।
     * 
     * @return विवरण (String में)
     */
    public String getDescription() {
        return description;
    }

    /**
     * भूमिका का विवरण सेट करता है।
     * 
     * @param description भूमिका का विवरण सेट करने के लिए
     */
    public void setDescription(String description) {
        this.description = description;
    }

    /**
     * BaseDTO कक्षा से विरासत में मिली getKey() विधि का कार्यान्वयन, 
     * जो भूमिका का अद्वितीय पहचान प्रदर्शित करती है।
     * 
     * @return id (String में)
     */
    @Override
    public String getKey() {
        return String.valueOf(id);
    }

    /**
     * BaseDTO कक्षा से विरासत में मिली getValue() विधि का कार्यान्वयन, 
     * जो भूमिका के नाम को प्रदर्शित करती है।
     * 
     * @return नाम (String में)
     */
    @Override
    public String getValue() {
        return name;
    }
}
```

### कोड का व्याख्या

- **RoleDTO कक्षा**: यह कक्षा उपयोगकर्ता की भूमिकाओं का प्रतिनिधित्व करती है। यह डेटाबेस तालिका "ST_ROLE" के साथ मैप होती है और उपयोगकर्ता के विभिन्न भूमिकाओं की जानकारी संग्रहित करती है।

- **स्थिरांक**: `ADMIN`, `STUDENT`, और `COLLEGE` भूमिकाओं को दर्शाने के लिए स्थिरांक (constants) हैं। ये स्थिरांक वर्ग के अन्य हिस्सों में भूमिकाओं की पहचान में मदद करते हैं।

- **फील्ड्स**:
  - `name`: भूमिका का नाम है, जो अधिकतम 50 वर्णों तक हो सकता है।
  - `description`: भूमिका का विवरण है, जो अधिकतम 255 वर्णों तक हो सकता है।

- **गेटर्स और सेटर्स**: `getName()`, `setName()`, `getDescription()`, और `setDescription()` विधियाँ हैं, जो नाम और विवरण को प्राप्त और सेट करने की अनुमति देती हैं।

- **getKey() और getValue() विधियाँ**: ये विधियाँ `BaseDTO` कक्षा से विरासत में ली गई हैं। `getKey()` विधि भूमिका के अद्वितीय पहचान को प्रदर्शित करती है, जबकि `getValue()` विधि भूमिका के नाम को लौटाती है। ये विधियाँ ड्रॉपडाउन लिस्ट में उपयोगकर्ता की भूमिकाओं को प्रदर्शित करने में मदद करती हैं। 
