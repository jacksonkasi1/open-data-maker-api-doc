# Quick Search College API

## API Endpoint

```markdown
https://api.data.gov/ed/collegescorecard/v1/schools.json?api_key={{API_KEY}}&school.name=New%20York&school.degrees_awarded.predominant=2,1&fields=id,school.name,2013.student.size&page=1&per_page=10&sort=school.name:asc
```

## API Query Parameters

```json
{
  "api_key": "{{API_KEY}}",
  "school.name":"New York",
  "school.degrees_awarded.predominant": "2,3",
  "fields": "id,school.name,2021.student.size",
  "page": 1,
  "per_page": 10
}
```

**note**: 2020.student.size (year will dynamic change, but data only available up to 2020)

> Replace \{{API\_KEY\}} with your actual API key to access the data.



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
