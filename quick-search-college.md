# Quick Search College API

## API Endpoint

```markdown
https://api.data.gov/ed/collegescorecard/v1/schools.json?api_key={{API_KEY}}&school.name=New%20York&fields=id,school.name,school.city,school.state&page=1&per_page=10&sort=school.name:asc
```

## API Query Parameters

```json
{
  "api_key": "{{API_KEY}}",
  "school.name":"New York",
  "fields": "id,school.name,school.city,school.state",
  "page": 1,
  "per_page": 10
}
```

**note**: 2020.student.size (year will dynamic change, but data only available up to 2020)

> Replace \{{API\_KEY\}} with your actual API key to access the data.



<details>

<summary>Response:</summary>



```json
{
    "metadata": {
        "page": 1,
        "total": 19,
        "per_page": 10
    },
    "results": [
        {
            "school.name": "New York Institute of Massage Inc",
            "school.city": "Williamsville",
            "school.state": "NY",
            "id": 431071
        },
        {
            "school.name": "New York Medical Career Training Center",
            "school.city": "Flushing",
            "school.state": "NY",
            "id": 457800
        },
        {
            "school.name": "New York School for Medical and Dental Assistants",
            "school.city": "Long Island City",
            "school.state": "NY",
            "id": 193858
        },
        {
            "school.name": "New York School of Esthetics & Day Spa",
            "school.city": "white plains",
            "school.state": "NY",
            "id": 475404
        },
        {
            "school.name": "New York School of Interior Design",
            "school.city": "New York",
            "school.state": "NY",
            "id": 194116
        },
        {
            "school.name": "New York Seminary",
            "school.city": "Brooklyn",
            "school.state": "NY",
            "id": 493798
        },
        {
            "school.name": "Robert Fiance Beauty Schools-West New York",
            "school.city": "West New York",
            "school.state": "NJ",
            "id": 185767
        },
        {
            "school.name": "SAE Institute of Technology-New York",
            "school.city": "New York",
            "school.state": "NY",
            "id": 459462
        },
        {
            "school.name": "School of Professional Horticulture New York Botanical Garden",
            "school.city": "Bronx",
            "school.state": "NY",
            "id": 392354
        }
    ]
}
```



</details>



**MORE INFO** 🧠:

#### Word and substring matches on `autocomplete` fields

Certain text fields in the dataset - those with the `autocomplete` data type - allow querying with a list of words. To search for a given word or string of words in those fields, just provide a list of space-separated words. This will return all records where the given field contains the given words as part of a string. **Note that all given words have to be at least three characters long.**

For example: To search for school names containing the words `New York`, use this parameter: `school.name=New%20York` (`%20` is a URL-encoded space) This will match all of these names:

* `New York College of Health Professions`
* `American Academy of Dramatic Arts-New York`
* `School of Professional Horticulture at the New York Botanical Garden`
* `The New College of York` (because the parameter words don't have to be found together)
* `Royal College of New Yorkminster` (because parameter words are matched as parts of other words)

but not this name:

* `New England School of Arts` (because `York` is missing)



***



### College fields:

* `id`
* `school.name`
* `school.city`
* `school.state`
* `2013.student.size ( max year up to 2020 )`
* `latest.student.size`
* `school.branches`
* `school.locale`
* `school.ownership`
* `school.degrees_awarded.predominant`
* `latest.academics.program_reporter.programs_offered`
* `latest.cost.avg_net_price.overall`
* `latest.completion.consumer_rate`
* `latest.earnings.10_yrs_after_entry.median`
* `latest.earnings.6_yrs_after_entry.percent_greater_than_25000`
* `school.under_investigation`
* `latest.completion.outcome_percentage_suppressed.all_students.8yr.award_pooled`
* `latest.completion.rate_suppressed.four_year`
* `latest.completion.rate_suppressed.lt_four_year_150percent`
* `latest.programs.cip_4_digit`



* `location.lon` - Latitude
* `location.lat` - Longitude
* `ope8_id`   - 8-digit OPE ID for institution
* `ope6_id`    - 6-digit OPE ID for institution



