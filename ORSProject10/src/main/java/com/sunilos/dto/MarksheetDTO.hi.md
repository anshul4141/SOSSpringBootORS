```java
package com.sunilos.dto;

import javax.persistence.Column;
import javax.persistence.Entity;
import javax.persistence.Table;

/**
 * MarksheetDTO क्लास एक मार्कशीट के लिए डेटा ट्रांसफर ऑब्जेक्ट (DTO) है।
 * यह डेटाबेस में "ST_MARKSHEET" तालिका के लिए एक स्थायी ऑब्जेक्ट है।
 * 
 * @author SunilOS
 * @version 1.0
 * @Copyright (c) SunilOS
 */
@Entity
@Table(name = "ST_MARKSHEET")
public class MarksheetDTO extends BaseDTO {

    /**
     * छात्र का रोल नंबर।
     */
    @Column(name = "ROLL_NO", length = 20)
    protected String rollNo = null;

    /**
     * छात्र का नाम।
     */
    @Column(name = "NAME", length = 50)
    protected String name = null;

    /**
     * भौतिकी में अंक।
     */
    @Column(name = "PHYSICS")
    protected Integer physics;

    /**
     * रसायन विज्ञान में अंक।
     */
    @Column(name = "CHEMISTRY")
    protected Integer chemistry;

    /**
     * गणित में अंक।
     */
    @Column(name = "MATHS")
    protected Integer maths;

    /**
     * छात्र की आईडी जो इस मार्कशीट से संबंधित है।
     */
    @Column(name = "STUDENT_ID")
    protected Long studentId;

    /**
     * छात्र आईडी प्राप्त करें।
     * 
     * @return छात्र आईडी (Long के रूप में)
     */
    public Long getStudentId() {
        return studentId;
    }

    /**
     * छात्र आईडी सेट करें।
     * 
     * @param studentId छात्र के लिए सेट करने के लिए आईडी
     */
    public void setStudentId(Long studentId) {
        this.studentId = studentId;
    }

    /**
     * छात्र का रोल नंबर प्राप्त करें।
     * 
     * @return रोल नंबर (String के रूप में)
     */
    public String getRollNo() {
        return rollNo;
    }

    /**
     * छात्र का रोल नंबर सेट करें।
     * 
     * @param rollNo छात्र के लिए सेट करने के लिए रोल नंबर
     */
    public void setRollNo(String rollNo) {
        this.rollNo = rollNo;
    }

    /**
     * छात्र का नाम प्राप्त करें।
     * 
     * @return नाम (String के रूप में)
     */
    public String getName() {
        return name;
    }

    /**
     * छात्र का नाम सेट करें।
     * 
     * @param name छात्र के लिए सेट करने के लिए नाम
     */
    public void setName(String name) {
        this.name = name;
    }

    /**
     * भौतिकी में अंक प्राप्त करें।
     * 
     * @return भौतिकी के अंक (Integer के रूप में)
     */
    public Integer getPhysics() {
        return physics;
    }

    /**
     * भौतिकी में अंक सेट करें।
     * 
     * @param physics छात्र के लिए सेट करने के लिए भौतिकी के अंक
     */
    public void setPhysics(Integer physics) {
        this.physics = physics;
    }

    /**
     * रसायन विज्ञान में अंक प्राप्त करें।
     * 
     * @return रसायन विज्ञान के अंक (Integer के रूप में)
     */
    public Integer getChemistry() {
        return chemistry;
    }

    /**
     * रसायन विज्ञान में अंक सेट करें।
     * 
     * @param chemistry छात्र के लिए सेट करने के लिए रसायन विज्ञान के अंक
     */
    public void setChemistry(Integer chemistry) {
        this.chemistry = chemistry;
    }

    /**
     * गणित में अंक प्राप्त करें।
     * 
     * @return गणित के अंक (Integer के रूप में)
     */
    public Integer getMaths() {
        return maths;
    }

    /**
     * गणित में अंक सेट करें।
     * 
     * @param maths छात्र के लिए सेट करने के लिए गणित के अंक
     */
    public void setMaths(Integer maths) {
        this.maths = maths;
    }

    /**
     * मार्कशीट का अद्वितीय कुंजी (आईडी) स्ट्रिंग के रूप में लौटाता है।
     * 
     * @return आईडी (String के रूप में)
     */
    public String getKey() {
        return id + "";
    }

    /**
     * मार्कशीट का मूल्य प्रतिनिधित्व लौटाता है, जो 
     * रोल नंबर को दर्शाता है।
     * 
     * @return रोल नंबर (String के रूप में)
     */
    public String getValue() {
        return rollNo;
    }
}
```

### कोड व्याख्या

- **MarksheetDTO क्लास**: यह क्लास एक डेटा ट्रांसफर ऑब्जेक्ट (DTO) है जो मार्कशीट का प्रतिनिधित्व करती है। यह डेटाबेस में "ST_MARKSHEET" तालिका से मैप की गई है और एक छात्र के अंकों की जानकारी रखती है।

- **फील्ड्स**:
  - `rollNo`: यह फील्ड छात्र का रोल नंबर संग्रहीत करती है, जिसकी अधिकतम लंबाई 20 अक्षर है।
  - `name`: यह फील्ड छात्र का नाम संग्रहीत करती है, जिसकी अधिकतम लंबाई 50 अक्षर है।
  - `physics`: यह फील्ड भौतिकी में छात्र के अंकों को रखती है।
  - `chemistry`: यह फील्ड रसायन विज्ञान में छात्र के अंकों को रखती है।
  - `maths`: यह फील्ड गणित में छात्र के अंकों को रखती है।
  - `studentId`: यह फील्ड उस छात्र की आईडी को संदर्भित करती है जो इस मार्कशीट से संबंधित है।

- **गेटर्स और सेटर्स**: ये मेथड निजी फील्ड्स तक पहुँच प्रदान करते हैं, जिससे अन्य क्लासें मानों को प्राप्त और अपडेट कर सकती हैं।

- **getKey() और getValue() मेथड्स**:
  - `getKey()`: मार्कशीट की अद्वितीय पहचानकर्ता (आईडी) को स्ट्रिंग के रूप में लौटाता है।
  - `getValue()`: रोल नंबर को स्ट्रिंग के रूप में लौटाता है, जो इस मार्कशीट से संबंधित मूल्य को दर्शाता है।
