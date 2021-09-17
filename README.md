# pump-it-up
Solution for  Pump it Up - Data Mining the Water Table challenge of drivendata<br> 
Repository: https://github.com/SasmithaDasanayaka/pump-it-up <br> 
Used models: RandomForestClassifier, XGBClassifier (xgboost), KNeighborsClassifier

## Preprocessing 

#### Identified categorical and numerical features
#### Handled missing values: Analysed missing value columns and used mean, median tranformations to fill missing values.
#### Used label encoding and one hot encoding to handle categorical data.
#### Introduced new category to handle some data in columns. i.e. `other` category to `installer` with 0.0 value.
#### Transformed all categorial names to lowercase to avoid issues while encoding.
#### Removed similar features.
* `wpt_name`
* `num_private`
* `subvillage`
* `region_code`
* `recorded_by`
* `management_group`
* `extraction_type_class`
* `extraction_type`
* `scheme_name`
* `quality_group`
* `source_type`
* `source_class`
* `waterpoint_type_group`
* `public_meeting`
* `permit`
#### used min-max normalization to ensure features have same scale.
* `amount_tsh`
* `gps_height`
* `population`
### Removed features which did not have specific value.
* `wpt_name`  - 45684 unique values.
* `scheme_name` - many nan values.
* `amount_tsh` - 70% of values are 0.
* `date_recorded` - not related with pumps
* `num_private` - 99% of data are 0.
* `recorded_by` - include only one value.

## Feature Engineering

#### Checked mutual informations
#### Created new feataures by transfomations. i.e. new column named `operation_years` created from `date_recorded` and `construction_year`
#### Target encoded - i.e. target encoded `ward` since it has considerable amount of unique values.
