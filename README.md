# Search fields:



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
*
