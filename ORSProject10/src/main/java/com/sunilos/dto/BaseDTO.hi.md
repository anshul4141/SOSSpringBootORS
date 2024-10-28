```java
package com.sunilos.dto;

import java.io.Serializable;
import java.sql.Timestamp;
import javax.persistence.Column;
import javax.persistence.GeneratedValue;
import javax.persistence.Id;
import javax.persistence.MappedSuperclass;
import org.hibernate.annotations.GenericGenerator;
import org.springframework.data.annotation.CreatedDate;
import org.springframework.data.annotation.LastModifiedDate;

/**
 * सभी डेटा ट्रांसफर ऑब्जेक्ट्स (DTOs) के लिए एब्स्ट्रैक्ट बेस क्लास।
 * यह क्लास सामान्य गुण और विधियां प्रदान करता है जो सभी विशिष्ट DTOs द्वारा इनहेरिट किए जाते हैं।
 * इसमें रिकॉर्ड के निर्माण और संशोधन को ट्रैक करने के लिए फ़ील्ड्स शामिल हैं और यह लिस्टिंग और 
 * तुलना के लिए सामान्य इंटरफेस लागू करता है।
 * 
 * Serializable ऑब्जेक्ट सीरियलाइज़ेशन के लिए, DropdownList को लिस्टिंग वैल्यू के लिए,
 * और Comparable को सॉर्टिंग के लिए लागू करता है।
 * 
 * @लेखक SunilOS
 * @संस्करण 1.0
 */
@MappedSuperclass
public abstract class BaseDTO implements Serializable, DropdownList, Comparable<BaseDTO> {

    /**
     * प्रत्येक रिकॉर्ड के लिए अद्वितीय पहचानकर्ता।
     * Hibernate द्वारा जनरेट किया गया एक नॉन-बिजनेस प्राइमरी की उपयोग करता है।
     */
    @Id
    @GenericGenerator(name = "hiIncrement", strategy = "increment")
    @GeneratedValue(generator = "hiIncrement")
    @Column(name = "ID", unique = true, nullable = false)
    protected long id;

    /**
     * इस रिकॉर्ड को बनाने वाले उपयोगकर्ता का यूजर आईडी संग्रहीत करता है।
     */
    @Column(name = "CREATED_BY", length = 50)
    protected String createdBy;

    /**
     * इस रिकॉर्ड को अंतिम बार संशोधित करने वाले उपयोगकर्ता का यूजर आईडी संग्रहीत करता है।
     */
    @Column(name = "MODIFIED_BY", length = 50)
    protected String modifiedBy;

    /**
     * जब रिकॉर्ड बनाया गया था उस समय का टाइमस्टैम्प।
     * रिकॉर्ड निर्माण के दौरान पर्सिस्टेंस फ्रेमवर्क द्वारा स्वचालित रूप से सेट किया जाता है।
     */
    @CreatedDate
    @Column(name = "CREATED_DATETIME")
    protected Timestamp createdDatetime;

    /**
     * इस रिकॉर्ड में किया गया अंतिम संशोधन का टाइमस्टैम्प।
     * जब रिकॉर्ड संशोधित होता है तो पर्सिस्टेंस फ्रेमवर्क द्वारा स्वचालित रूप से अपडेट होता है।
     */
    @LastModifiedDate
    @Column(name = "MODIFIED_DATETIME")
    protected Timestamp modifiedDatetime;

    /**
     * रिकॉर्ड के लिए अद्वितीय पहचानकर्ता प्राप्त करता है।
     * 
     * @return रिकॉर्ड का id
     */
    public long getId() {
        return id;
    }

    /**
     * रिकॉर्ड के लिए अद्वितीय पहचानकर्ता सेट करता है।
     * 
     * @param id सेट करने के लिए नया id
     */
    public void setId(long id) {
        this.id = id;
    }

    /**
     * उस उपयोगकर्ता का ID प्राप्त करता है जिसने यह रिकॉर्ड बनाया था।
     * 
     * @return उस उपयोगकर्ता का ID जिसने यह रिकॉर्ड बनाया था
     */
    public String getCreatedBy() {
        return createdBy;
    }

    /**
     * उस उपयोगकर्ता का ID सेट करता है जिसने यह रिकॉर्ड बनाया था।
     * 
     * @param createdBy सेट करने के लिए उपयोगकर्ता का ID
     */
    public void setCreatedBy(String createdBy) {
        this.createdBy = createdBy;
    }

    /**
     * उस उपयोगकर्ता का ID प्राप्त करता है जिसने यह रिकॉर्ड अंतिम बार संशोधित किया था।
     * 
     * @return उस उपयोगकर्ता का ID जिसने यह रिकॉर्ड अंतिम बार संशोधित किया था
     */
    public String getModifiedBy() {
        return modifiedBy;
    }

    /**
     * उस उपयोगकर्ता का ID सेट करता है जिसने यह रिकॉर्ड अंतिम बार संशोधित किया था।
     * 
     * @param modifiedBy सेट करने के लिए उपयोगकर्ता का ID
     */
    public void setModifiedBy(String modifiedBy) {
        this.modifiedBy = modifiedBy;
    }

    /**
     * इस रिकॉर्ड के निर्माण का टाइमस्टैम्प प्राप्त करता है।
     * 
     * @return रिकॉर्ड निर्माण का टाइमस्टैम्प
     */
    public Timestamp getCreatedDatetime() {
        return createdDatetime;
    }

    /**
     * इस रिकॉर्ड के निर्माण का टाइमस्टैम्प सेट करता है।
     * 
     * @param createdDatetime सेट करने के लिए टाइमस्टैम्प
     */
    public void setCreatedDatetime(Timestamp createdDatetime) {
        this.createdDatetime = createdDatetime;
    }

    /**
     * इस रिकॉर्ड में अंतिम बार संशोधित किए गए टाइमस्टैम्प को प्राप्त करता है।
     * 
     * @return अंतिम संशोधन का टाइमस्टैम्प
     */
    public Timestamp getModifiedDatetime() {
        return modifiedDatetime;
    }

    /**
     * इस रिकॉर्ड में अंतिम बार संशोधित किए गए टाइमस्टैम्प को सेट करता है।
     * 
     * @param modifiedDatetime सेट करने के लिए टाइमस्टैम्प
     */
    public void setModifiedDatetime(Timestamp modifiedDatetime) {
        this.modifiedDatetime = modifiedDatetime;
    }

    /**
     * एक विशिष्ट मूल्य के आधार पर इस DTO की तुलना अगले DTO से करता है,
     * जिसे सबक्लास द्वारा परिभाषित किया जाना चाहिए।
     * 
     * @param next तुलना करने के लिए अगला DTO
     * @return नकारात्मक संख्या, शून्य, या सकारात्मक संख्या इस वस्तु की तुलना में
     *         अगले ऑब्जेक्ट के कम, बराबर, या अधिक होने पर आधारित है
     */
    public int compareTo(BaseDTO next) {
        return getValue().compareTo(next.getValue());
    }
}
``` 

### विवरण

1. **क्लास-स्तरीय Javadoc**: `BaseDTO` का उच्च-स्तरीय अवलोकन प्रदान करता है, जिसमें लेखक, संस्करण और इनहेरिटेंस संरचना शामिल है।
2. **`@MappedSuperclass` एनोटेशन**: इस क्लास को एक मैप्ड सुपरक्लास के रूप में चिह्नित करता है ताकि इसकी मैपिंग को सबक्लासेज़ द्वारा इनहेरिट किया जा सके, बिना इसके लिए एक डेटाबेस टेबल बनाए।
3. **फ़ील्ड्स**:
   - `id`: Hibernate का `GenericGenerator` का उपयोग करके इनक्रीमेंटिंग ID स्ट्रेटेजी का उपयोग करता है।
   - `createdBy`, `modifiedBy`: रिकॉर्ड बनाने वाले और अंतिम बार संशोधित करने वाले उपयोगकर्ता का ट्रैक रखता है।
   - `createdDatetime`, `modifiedDatetime`: स्वचालित रूप से निर्माण और संशोधन के टाइमस्टैम्प सेट करता है।
4. **गेटर और सेटर विधियाँ**: प्रत्येक फ़ील्ड के लिए पहुंच और संशोधन प्रदान करती हैं, जिनमें प्रत्येक विधि का उद्देश्य समझाने के लिए JavaDocs होते हैं।
5. **`compareTo` विधि**: `getValue` विधि (संभवतः सबक्लास में परिभाषित) के आधार पर `BaseDTO` उदाहरणों की तुलना करता है। यह विधि DTOs के लिए सॉर्टिंग सक्षम करती है।
