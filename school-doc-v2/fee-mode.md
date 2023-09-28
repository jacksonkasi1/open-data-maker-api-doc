# Fee Mode

## SchoolFee collection

```javascript
# SchoolFee collection
{
  "_id": ObjectId,  # Unique identifier for the school fee document
  "UNITID": String,  # Unique identification number of the institution (foreign key)
  "tuition1": Number,  # Charges to full-time undergraduate students for the full academic year 2022-23 (In-district average tuition)
  "fee1": Number,  # Charges to full-time undergraduate students for the full academic year 2022-23 (In-district required fees)
  "hrchg1": Number,  # Per credit hour charge for part-time undergraduate students (In-district per credit hour charge)
  "tuition2": Number,  # Charges to full-time undergraduate students for the full academic year 2022-23 (In-state average tuition)
  "fee2": Number,  # Charges to full-time undergraduate students for the full academic year 2022-23 (In-state required fees)
  "hrchg2": Number,  # Per credit hour charge for part-time undergraduate students (In-state per credit hour charge)
  "tuition3": Number,  # Charges to full-time undergraduate students for the full academic year 2022-23 (Out-of-state average tuition)
  "fee3": Number,  # Charges to full-time undergraduate students for the full academic year 2022-23 (Out-of-state required fees)
  "hrchg3": Number  # Per credit hour charge for part-time undergraduate students (Out-of-state per credit hour charge)
}

```

## School collection

```javascript
{ 
"_id": ObjectId, # Unique identifier for the school document 
"UNITID": String, # Unique identification number of the institution (primary key)
"name": String, # Name of the school 
"location": String, # Location of the school 
"other_fields": Any # Other fields specific to the school 
}
```
