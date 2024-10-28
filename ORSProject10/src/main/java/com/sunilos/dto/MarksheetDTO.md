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

### Code Explanation

- **MarksheetDTO Class**: This class is a Data Transfer Object (DTO) that represents a marksheet. It is mapped to the "ST_MARKSHEET" table in the database and contains information about a student's marks.

- **Fields**:
  - `rollNo`: This field stores the roll number of the student, with a maximum length of 20 characters.
  - `name`: This field stores the name of the student, with a maximum length of 50 characters.
  - `physics`: This field holds the student's marks in physics.
  - `chemistry`: This field holds the student's marks in chemistry.
  - `maths`: This field holds the student's marks in mathematics.
  - `studentId`: This field is a reference to the ID of the student associated with this marksheet.

- **Getters and Setters**: These methods provide access to the private fields, allowing other classes to retrieve and update the values.

- **getKey() and getValue() Methods**:
  - `getKey()`: Returns the unique identifier (ID) of the marksheet as a string.
  - `getValue()`: Returns the roll number as a string representation, which serves as the value associated with this marksheet.
