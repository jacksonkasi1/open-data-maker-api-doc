# List it for mogno db

1. UNITID: Unique identification number for each school.
2. INSTNM: Name of the institution.
3. ADDR: Address of the institution.
4. CITY: City where the institution is located.
5. STABBR: State abbreviation where the institution is located.
6. ZIP: ZIP code of the institution.
7. WEBADDR: Website address of the institution.
8. ADMINURL: URL for administrative information.
9. FAIDURL: URL for financial aid information.
10. APPLURL: URL for the application process.
11. NPRICURL: URL for the net price calculator.
12. DISAURL: URL for disability services.
13. UGOFFER: Indicator of undergraduate programs offered.
14. GROFFER: Indicator of graduate programs offered.
15. HDEGOFR1: Highest degree offered by the institution.
16. DEGGRANT: Indicator of degree-granting status.
17. LOCALE: Locale code indicating the location type of the institution.
18. OPENPUBL: Indicator of whether the institution is open to the public.
19. ACT: ACT composite score range for admitted students.
20. INSTCAT: Institutional category.
21. C21BASIC: Carnegie Classification - Basic.
22. C21IPUG: Carnegie Classification - Undergraduate Instructional Program.
23. C21IPGRD: Carnegie Classification - Graduate Instructional Program.
24. C21UGPRF: Carnegie Classification - Undergraduate Profile.
25. C21ENPRF: Carnegie Classification - Enrollment Profile.
26. C21SZSET: Carnegie Classification - Size and Setting.
27. INSTSIZE: Size of the institution.
28. F1SYSTYP: Federal System Code.
29. F1SYSNAM: Federal System Name.
30. F1SYSCOD: Federal System Code.
31. CBSA: Core-Based Statistical Area.
32. CBSATYPE: CBSA Type.
33. CSA: Combined Statistical Area.
34. COUNTYCD: County Code.
35. COUNTYNM: County Name.
36. LONGITUD: Longitude coordinate of the institution.
37. LATITUDE: Latitude coordinate of the institution.
38. SECTOR: Institutional category (public, private not-for-profit, private for-profit).
39. HLOFFER: Highest level of offering (e.g., associate's, bachelor's, master's, doctor's degree).
40. HBCU: Code indicating if the institution is a Historically Black College or University (HBCU).
41. HOSPITAL: Code indicating if the institution has a hospital.



These fields can be helpful for students in various ways:

* INSTNM, ADDR, CITY, STABBR, ZIP: Provide basic contact and location information for the institution.
* WEBADDR: Allows students to visit the institution's official website for comprehensive information.
* ADMINURL: Provides access to administrative resources and contact details.
* FAIDURL: Offers information about financial aid options and resources.
* APPLURL: Provides guidance on the application process and requirements.
* NPRICURL: Allows students to calculate the net price of attending the institution.
* DISAURL: Provides information about disability services and accommodations available.
* UGOFFER, GROFFER, HDEGOFR1: Indicate the types of programs and degrees offered by the institution.
* DEGGRANT: Indicates if the institution grants degrees.
* LOCALE: Provides information about the location type of the institution (rural, suburban, etc.).
* ACT: Provides an idea of the ACT score range for admitted students.
* INSTCAT: Categorizes the institution based on its characteristics.
* INSTSIZE: Provides information about the size of the institution.
* F1SYSTYP, F1SYSNAM, F1SYSCOD: Federal system codes and names provide additional classification information.
* CBSA, CBSATYPE, CSA, COUNTYCD, COUNTYNM: Geographic information that helps identify the location of the institution.
* LONGITUD, LATITUDE: Coordinates for mapping the institution's location.



```javascript
const mongoose = require('mongoose');

const SchoolSchema = new mongoose.Schema({
  UNITID: Number,
  INSTNM: String,
  IALIAS: String,
  ADDR: String,
  CITY: String,
  STABBR: String,
  ZIP: String,
  OPEID: Number,
  OPEFLAG: Number,
  WEBADDR: String,
  ADMINURL: String,
  FAIDURL: String,
  APPLURL: String,
  NPRICURL: String,
  DISAURL: String,
  UGOFFER: {
    type: Number,
    enum: [0, 1, 2] // 0: Not offered, 1: Offered, 2: Unknown
  },
  GROFFER: {
    type: Number,
    enum: [0, 1, 2] // 0: Not offered, 1: Offered, 2: Unknown
  },
  HDEGOFR1: {
    type: Number,
    enum: [0, 1, 2, 3, 4, 5] // 0: Non-degree-granting, 1-4: Associate to Doctor's degree, 5: Unknown
  },
  DEGGRANT: {
    type: Number,
    enum: [0, 1, 2] // 0: Not a degree-granting institution, 1: Degree-granting institution, 2: Unknown
  },
  HBCU: {
    type: Number,
    enum: [0, 1, 2] // 0: Not an HBCU, 1: HBCU, 2: Unknown
  },
  HOSPITAL: {
    type: Number,
    enum: [0, 1, 2] // 0: No hospital, 1: Hospital, 2: Unknown
  },
  MEDICAL: {
    type: Number,
    enum: [0, 1, 2] // 0: Not medical, 1: Medical, 2: Unknown
  },
  TRIBAL: {
    type: Number,
    enum: [0, 1, 2] // 0: Not a tribal institution, 1: Tribal institution, 2: Unknown
  },
  LOCALE: {
    type: Number,
    enum: [11, 12, 13, 21, 22, 23, 31, 32, 33, 41, 42, 43, 44, 51, 52, 53] // See documentation for locale codes
  },
  OPENPUBL: {
    type: Number,
    enum: [0, 1, 2] // 0: Not open to the public, 1: Open to the public, 2: Unknown
  },
  ACT: Number,
  NEWID: Number,
  DEATHYR: Number,
  CLOSEDAT: Number,
  CYACTIVE: Number,
  POSTSEC: Number,
  PSEFLAG: Number,
  PSET4FLG: Number,
  RPTMTH: Number,
  INSTCAT: Number,
  C21BASIC: Number,
  C21IPUG: Number,
  C21IPGRD: Number,
  C21UGPRF: Number,
  C21ENPRF: Number,
  C21SZSET: Number,
  C18BASIC: Number,
  C15BASIC: Number,
  CCBASIC: Number,
  CARNEGIE: Number,
  LANDGRNT: Number,
  INSTSIZE: Number,
  F1SYSTYP: Number,
  F1SYSNAM: String,
  F1SYSCOD: Number,
  CBSA: Number,
  CBSATYPE: Number,
  CSA: Number,
  COUNTYCD: Number,
  COUNTYNM: String,
  CNGDSTCD: Number,
  LONGITUD: Number,
  LATITUDE: Number,
  DFRCGID: Number,
  DFRCUSCG: Number
});

const SchoolModel = mongoose.model('School', SchoolSchema);

module.exports = SchoolModel;
```





```
 ACT: Number,
```

```
  NEWID: Number,
```

```
  DEATHYR: Number,
```

```
  CLOSEDAT: Number,
```

```
  CYACTIVE: Number,
```

```
  POSTSEC: Number,
```

```
  PSEFLAG: Number,
```

```
  PSET4FLG: Number,
```

```
  RPTMTH: Number,
```

```
  INSTCAT: Number,
```

```
  C21BASIC: Number,
```

```
  C21IPUG: Number,
```

```
  C21IPGRD: Number,
```

```
  C21UGPRF: Number,
```

```
  C21ENPRF: Number,
```

```
  C21SZSET: Number,
```

```
  C18BASIC: Number,
```

```
  C15BASIC: Number,
```

```
  CCBASIC: Number,
```

```
  CARNEGIE: Number,
```

```
  LANDGRNT: Number,
```

```
  INSTSIZE: Number,
```

```
  F1SYSTYP: Number,
```

```
  F1SYSNAM: String,
```

```
  F1SYSCOD: Number,
```

```
  CBSA: Number,
```

```
  CBSATYPE: Number,
```

```
  CSA: Number,
```

```
  COUNTYCD: Number,
```

```
  COUNTYNM: String,
```

```
  CNGDSTCD: Number,
```

```
  LONGITUD: Number,
```

```
  LATITUDE: Number,
```

```
  DFRCGID: Number,
```

```
  DFRCUSCG: Number
```



Here is an explanation of some of the fields in the provided MongoDB model for the School schema:

1. ACT: This field represents the average ACT score of students at the school. It is of type Number.
2. INSTCAT: This field represents the institutional category of the school. The specific values for this field are not provided in the model, but it could be a numerical code representing different categories such as "1" for public institutions, "2" for private nonprofit institutions, and so on.
3. CARNEGIE: This field represents the Carnegie Classification of the school. The Carnegie Classification is a framework used to categorize higher education institutions in the United States based on various factors such as size, academic programs, and research activity. The specific values for this field are not provided in the model, but it could be a numerical code representing different classifications.
4. INSTSIZE: This field represents the size of the institution, typically based on the number of enrolled students. It is of type Number.
5. COUNTYCD: This field represents the county code where the school is located. It is of type Number.
6. COUNTYNM: This field represents the name of the county where the school is located. It is of type String.
7. LONGITUD: This field represents the longitude coordinate of the school's location. It is of type Number.
8. LATITUDE: This field represents the latitude coordinate of the school's location. It is of type Number.
9. CBSA: This field represents the Core-Based Statistical Area (CBSA) code associated with the school's location. CBSA is a geographical classification used by the U.S. Census Bureau. It is of type Number.
10. CSA: This field represents the Combined Statistical Area (CSA) code associated with the school's location. CSA is a broader geographical classification that combines adjacent CBSAs. It is of type Number.
11. F1SYSNAM: This field represents the name of the school system or district associated with the institution. It is of type String.

These fields provide additional information about the school, such as test scores, institutional characteristics, location details, and affiliations. The specific values for each field would depend on the data provided for each school in the database.

