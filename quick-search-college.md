# Quick Search College API

## API Endpoint

```markdown
https://api.data.gov/ed/collegescorecard/v1/schools.json?api_key={{API_KEY}}&school.degrees_awarded.predominant=2,3&fields=id,school.name,2021.student.size&page=1&per_page=10
```

## API Query Parameters

```json
{
  "api_key": "{{API_KEY}}",
  "school.degrees_awarded.predominant": "2,3",
  "fields": "id,school.name,2021.student.size",
  "page": 1,
  "per_page": 10
}
```

**note**: 2020.student.size (year will dynamic change, but data only available up to 2020)

> Replace {{API_KEY}} with your actual API key to access the data.