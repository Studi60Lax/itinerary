We'll be focusing on the 3 spreadsheets that contain a Location column, as this is most pertinent to the map. The tallies in the other two sheets are ancillary timeline data.

* A Frightful Number - H.F.
* A Frightful Number - The Three Kinsmen
* A Frightful Number - Plague

Our goal is to determine a consistent data model to store location/event data that we can store in CSV files and work with.

In an attempt to establish consistent fields and data formats, I propose the following for any data that goes on a map:

#### Year (date_year)

**Integer**

**Required** for sorting.

#### Month (date_month)

**Integer, 2 digits**

**Required** for sorting, even if it defaults to 01.

#### Date (date_day)

**Integer, 2 digits**

**Required** for sorting, even if it defaults to 01.

#### Season (season)

* `null`
* `winter`
* `spring`
* `summer`
* `fall`

#### Exact Month? (date_month_exact)

**Boolean**

If `false`, we should aspire to group such events on a timeline per **Season** (if provided) or **Year**.

#### Exact Date? (date_day_exact)

**Boolean**

If `false`, we should aspire to group such events on a timeline per **Month**.

#### Descriptive Date (date_descriptive)

**Text**

Matches the value provided in the initial spreadsheets.

*Ex: "End of November-Beginning of December", "January 10-17"*

#### Parish

**Text**

Matches the value provided in the initial spreadsheets. Displayed as metadata / is not used in timeline or location mapping.

Questions:

* Is there a way to define this more generically to be applicable for other projects?

#### Location (location_descriptive)

**Text**

Matches the value provided in the initial spreadsheets. Displayed as metadata / is not used in timeline or location mapping.

#### Location: Latitude (location_latitude)

**Float**

It will be necessary to obtain and store a latitude for each location on the map.

#### Location: Longitude (location_longitude)

**Float**

It will be necessary to obtain and store a longitude for each location on the map.

#### Page Number (source_page)

**Text**

Matches the value provided in the initial spreadsheets. Displayed as metadata / is not used in timeline or location mapping. Corresponds to an identified source.

*Ex: "84", "86-87"*

#### Source

**Integer**

Source should be an integer ID value corresponding to another dataset of sources. Displayed as metadata / is not used in timeline or location mapping. May be used to group location/event points on a timeline or map.

*Ex: "1"*

ID | Title | Author | Editor | Published | Location | Citation
---|-------|--------|--------|-----------|----------|---------
1|A Journal of the Plague Year|Defoe, Daniel|Ed. Cynthia Wall|Penguin, 2003|New York|Defoe, Daniel. A Journal of the Plague Year. Ed. Cynthia Wall. New York: Penguin, 2003.

#### Notes

**Text**

Freetext notes that match the values provided in the initial spreadsheets. Displayed as metadata / not used in timeline or location mapping.