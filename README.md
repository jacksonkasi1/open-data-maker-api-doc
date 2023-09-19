# Search filter options:



### Search fields:

<details>

<summary>sort</summary>



* asc&#x20;
* desc

***



**EX:**  [`https://api.data.gov/ed/collegescorecard/v1/schools.json?api_key={{API_KEY}}&sort=school.name:asc`](https://api.data.gov/ed/collegescorecard/v1/schools.json?api\_key=\{{API\_KEY\}}\&sort=school.name:asc)

\
**Note:** Sorting is only available on fields with the data type `integer`, `float`, `autocomplete` or `name`.

</details>

<details>

<summary>page &#x26; per_page &#x26; total ( meta data )</summary>



**page**  - search api  page id&#x20;

**per\_page** - data limit per page ( max 100 )

**total -** total page count for search\


***

\
**EX:** [`https://api.data.gov/ed/collegescorecard/v1/schools.json?api_key={{API_KEY}}&fields=id,school.name&page=1&per_page=10`](https://api.data.gov/ed/collegescorecard/v1/schools.json?api\_key=\{{API\_KEY\}}\&school.degrees\_awarded.predominant=2,3\&fields=id,school.name,2021.student.size\&page=1\&per\_page=10)



</details>

<details>

<summary>Geographic Filtering</summary>



**options**:&#x20;

* state
* zip
* distance



#### State ➡️



school.state\[]: AR

school.state\[]: AZ

school.state\[]: CA



**EX:** [`https://api.data.gov/ed/collegescorecard/v1/schools.json?api_key={{API_KEY}}&fields=id,school.name&school.state[]=AR&school.state[]=CA`](https://api.data.gov/ed/collegescorecard/v1/schools.json?api\_key=\{{API\_KEY\}}\&fields=id,school.name\&school.state\[]=AR\&school.state\[]=CA)



**Check for state list:**

* [https://countrystatecity.in/](https://countrystatecity.in/)
* [https://www.back4app.com/database/back4app/usa-by-state](https://www.back4app.com/database/back4app/usa-by-state)
* [https://www.npmjs.com/package/country-state-city](https://www.npmjs.com/package/country-state-city)



***



**Zip** ➡️



zip=16332



**EX**: [`https://api.data.gov/ed/collegescorecard/v1/schools.json?api_key={{API_KEY}}&fields=id,school.name&zip=16332`](https://api.data.gov/ed/collegescorecard/v1/schools.json?api\_key=\{{API\_KEY\}}\&fields=id,school.name\&zip=16332)



**Note**: us zip code only support



***



**Distance** ➡️



* distance=10mi

( or )

* distance=10km

mi = miles

km = kilometer



**EX**:  [`https://api.data.gov/ed/collegescorecard/v1/schools.json?api_key={{API_KEY}}&fields=id,school.name&zip=16332&distance=100mi`\
](https://api.data.gov/ed/collegescorecard/v1/schools.json?api\_key=\{{API\_KEY\}}\&fields=id,school.name\&zip=16332\&distance=100mi)

**Note:** For example, `zip=12345&distance=10mi` will return only those results within 10 miles of the center of the given zip code.



***



**MORE INFO 🧠:**



When the dataset includes a `location` at the root level (`location.lat` and `location.lon`) then the documents will be indexed geographically. You can use the `zip` and `distance` options to narrow query results down to those within a geographic area. For example, `zip=12345&distance=10mi` will return only those results within 10 miles of the center of the given zip code.

Additionally, you can request `location.lat` and `location.lon` in a search that includes a `fields` filter and it will return the record(s) with respective lat and/or lon coordinates.

**Additional Notes on Geographic Filtering**

* By default, any number passed in the `distance` parameter is treated as a number of miles, but you can specify miles or kilometers by appending `mi` or `km` respectively.
* Distances are calculated from the center of the given zip code, not the boundary.
* Only U.S. zip codes are supported.





</details>

<details>

<summary>Degree Types</summary>



![](<.gitbook/assets/image (2).png>)



## Undergraduate



programs.cip\_4\_digit.credential.level = 1

programs.cip\_4\_digit.credential.level = 2

programs.cip\_4\_digit.credential.level = 3



## Graduate



programs.cip\_4\_digit.credential.level = 4

programs.cip\_4\_digit.credential.level = 5

programs.cip\_4\_digit.credential.level = 6

programs.cip\_4\_digit.credential.level = 7

programs.cip\_4\_digit.credential.level = 8



<mark style="color:yellow;">**All Value :**</mark>

* [ ] 1 = `Undergraduate Certificate or Diploma`
* [ ] 2 = `Associate's Degree`
* [ ] 3 = `Bachelor's Degree`
* [ ] 4 = `Post-baccalaureate Certificate`
* [ ] 5 = `Master's Degree`
* [ ] 6 = `Doctoral Degree`
* [ ] 7 = `First Professional Degree`
* [ ] 8 = `Graduate/Professional Certificate`&#x20;



**EX:** [`https://api.data.gov/ed/collegescorecard/v1/schools.json?api_key={{API_KEY}}&fields=id,school.name&programs.cip_4_digit.credential.level=6`](https://api.data.gov/ed/collegescorecard/v1/schools.json?api\_key=\{{API\_KEY\}}\&fields=id,school.name\&programs.cip\_4\_digit.credential.level=6)



**Response:**&#x20;

```json
{
    "metadata": {
        "page": 0,
        "total": 12,
        "per_page": 2
    },
    "results": [
        {
            "school.name": "Dominican University New York",
            "school.city": "Orangeburg",
            "school.state": "NY",
            "id": 190761
        },
        {
            "school.name": "New York Institute of Technology",
            "school.city": "Old Westbury",
            "school.state": "NY",
            "id": 194091
        }
    ]
}
```



**EX of get with values:**

[`https://api.data.gov/ed/collegescorecard/v1/schools.json?api_key={{API_KEY}}&fields=id,school.name,school.city,school.state,school.zip,school.accreditor,location.lat,location.lon,programs.cip_4_digit.credential.title,programs.cip_4_digit.credential.level&page=0&per_page=10&programs.cip_4_digit.credential.level=6`](https://api.data.gov/ed/collegescorecard/v1/schools.json?api\_key=\{{API\_KEY\}}\&fields=id,school.name,school.city,school.state,school.zip,school.accreditor,location.lat,location.lon,programs.cip\_4\_digit.credential.title,programs.cip\_4\_digit.credential.level\&page=0\&per\_page=10\&programs.cip\_4\_digit.credential.level=6)



**Response:**&#x20;

```json
{
    "metadata": {
        "page": 0,
        "total": 1083,
        "per_page": 2
    },
    "results": [
        {
            "latest.programs.cip_4_digit": [
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                }
            ],
            "school.name": "Alabama A & M University",
            "school.city": "Normal",
            "school.state": "AL",
            "school.zip": "35762",
            "school.accreditor": "Southern Association of Colleges and Schools Commission on Colleges",
            "id": 100654,
            "location.lat": 34.783368,
            "location.lon": -86.568502
        },
        {
            "latest.programs.cip_4_digit": [
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                },
                {
                    "credential": {
                        "level": 6,
                        "title": "Doctoral Degree"
                    }
                }
            ],
            "school.name": "University of Alabama at Birmingham",
            "school.city": "Birmingham",
            "school.state": "AL",
            "school.zip": "35294-0110",
            "school.accreditor": "Southern Association of Colleges and Schools Commission on Colleges",
            "id": 100663,
            "location.lat": 33.505697,
            "location.lon": -86.799345
        }
    ]
}
```









</details>



