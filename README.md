# Search fields:



### Search fields:

<details>

<summary>sort</summary>

* asc&#x20;
* desc

***



**EX:**  [`https://api.data.gov/ed/collegescorecard/v1/schools.json?api_key={{API_KEY}}&sort=school.name:asc`](https://api.data.gov/ed/collegescorecard/v1/schools.json?api\_key=\{{API\_KEY\}}\&sort=school.name:asc)

</details>

<details>

<summary>page &#x26; per_page</summary>

**page**  - search api  page id&#x20;

**per\_page** - data limit per page ( max 100 )\


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
