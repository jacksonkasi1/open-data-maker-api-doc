# Final Fee Model with Doc



Below is a simplified summary of the fee-related information from the document "glofi-school-fee-info - Description (1).csv":

1. In-district Required fees (FEE1):
   * Description: Charges to full-time undergraduate students for the full academic year 2022-23.
   * Explanation: Fees charged to students residing in the locality where the institution is located. It may be a lower rate than in-state fees if offered by the institution.
2. In-state Required fees (FEE2):
   * Description: Charges to full-time undergraduate students for the full academic year 2022-23.
   * Explanation: Fees charged to students who meet the state's or institution's residency requirements.
3.  Out-of-state Required fees (FEE3):

    * Description: Charges to full-time undergraduate students for the full academic year 2022-23.
    * Explanation: Fees charged to students who do not meet the institution's or state's residency requirements.



## School Fee Model

```javascript
const mongoose = require('mongoose');

// Define the schema
const SchoolFeeSchema = new mongoose.Schema({
  type: {
    type: String,
    enum: ['in-district', 'in-state', 'out-of-state'],
    required: true,
  },
  description: {
    type: String,
    required: true,
  },
  academicYear: {
    type: String,
    required: true,
  },
  amount: {
    type: Number,
    required: true,
  },
});

// Create the model
const SchoolFee = mongoose.model('SchoolFee', SchoolFeeSchema);

module.exports = SchoolFee;

```



## Example Data:

```json

{
  UNITID: 12345,
  type: 'in-district',
  description: 'Charges to full-time undergraduate students for the full academic year 2022-23',
  academicYear: '2022-23',
  amount: 5000,
}
```



## Relation ship with School model&#x20;



```javascript
const mongoose = require('mongoose');

// Define the School schema
const SchoolSchema = new mongoose.Schema({
  UNITID: {
    type: Number,
    required: true,
    unique: true,
  },
  // Other fields of the School model
  // ...
});

// Define the SchoolFee schema
const SchoolFeeSchema = new mongoose.Schema({
  school: {
    type: mongoose.Schema.Types.ObjectId,
    ref: 'School',
    required: true,
  },
  type: {
    type: String,
    enum: ['in-district', 'in-state', 'out-of-state'],
    required: true,
  },
  description: {
    type: String,
    required: true,
  },
  academicYear: {
    type: String,
    required: true,
  },
  amount: {
    type: Number,
    required: true,
  },
});

// Create the models
const School = mongoose.model('School', SchoolSchema);
const SchoolFee = mongoose.model('SchoolFee', SchoolFeeSchema);

module.exports = { School, SchoolFee };
```



note: description no need in model

