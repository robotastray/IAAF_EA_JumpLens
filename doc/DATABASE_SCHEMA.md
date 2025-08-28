Following is the schema used for the JUMPLENS SQL tables.

# Table of Content 

1. [Tables](#1-tables)
2. [Tables Schema](#2-)
   
   2.1. [JUMPLENS_ATHLETES](#jumplens_athletes)
   
   2.2. [JUMPLENS_ATHLETES_PERFORMANCE](#jumplens_athletes_performance)
   
   2.3. [JUMPLENS_AVG_CONTACT_AND_FLIGHT_LENGTH](#jumplens_avg_contact_and_flight_length)
   
   2.4. [JUMPLENS_COMPETITIONS_DETAILS](#jumplens_competitions_details)
   
   2.5. [JUMPLENS_COM_VELOCITY_CHANGES](#jumplens_com_velocity_changes)
   
   2.6. [JUMPLENS_PHASE_DISTANCES](#jumplens_phase_distances)
   
   2.7. [JUMPLENS_TAKEOFF_VELOCITIES](#jumplens_takeoff_velocities)
   
   2.8. [JUMPLENS_LANDING_DISTANCE_VELOCITIES](#jumplens_landing_distance_velocities)
   
   2.9. [JUMPLENS_STRIDES_LENGTH](#jumplens_strides_length)
   
3. [Data Types Reference](#data-types-reference)
   
4. [Notes](#notes)

   
# 1.Tables {#1-tables}

The list of tables available are read-only. 
The RLS policy enables read only access for authenticated users only. 
Please note that the metrics were not measured from a real competition, the data avaialable are dummy for the porpuse of the demo 

| table_name                             |
| -------------------------------------- |
| JUMPLENS_ATHLETES|
| JUMPLENS_ATHLETES_PERFORMANCE|
| JUMPLENS_AVG_CONTACT_AND_FLIGHT_LENGTH |
| JUMPLENS_COMPETITIONS_DETAILS          |
| JUMPLENS_COM_VELOCITY_CHANGES          |
| JUMPLENS_PHASE_DISTANCES               |
| JUMPLENS_TAKEOFF_VELOCITIES            |
| JUMPLENS_LANDING_DISTANCE_VELOCITIES   |
| JUMPLENS_STRIDES_LENGTH                |

# Tables Schema 

## JUMPLENS_ATHLETES 

| column_name | data_type                | is_nullable | column_default    |
| ----------- | ------------------------ | ----------- | ----------------- |
| id          | uuid                     | NO          | gen_random_uuid() |
| created_at  | timestamp with time zone | NO          | now()             |
| athlete_id  | bigint                   | YES         | null              |
| name        | text                     | YES         | null              |
| surname     | text                     | YES         | null              |
| dob         | date                     | YES         | null              |
| club        | text                     | YES         | null              |
| event       | text                     | YES         | null              |
| country     | text                     | YES         | 'GBR'::text       |
| image       | text                     | YES         | null              |
| lead_coach  | text                     | YES         | null              |
| other_coach | text                     | YES         | null              |
| PB          | real                     | YES         | null              |
| gender      | text                     | YES         | null              |

## JUMPLENS_ATHLETES_PERFORMANCE

| column_name        | data_type                | is_nullable | column_default    |
| ------------------ | ------------------------ | ----------- | ----------------- |
| id                 | uuid                     | NO          | gen_random_uuid() |
| created_at         | timestamp with time zone | NO          | now()             |
| event_type         | text                     | YES         | null              |
| hop                | real                     | YES         | null              |
| step               | real                     | YES         | null              |
| jump               | real                     | YES         | null              |
| meeting_id         | bigint                   | YES         | null              |
| official_distance  | real                     | YES         | null              |
| effective_distance | real                     | YES         | null              |
| athlete_id         | bigint                   | YES         | null              |
| competition_type   | text                     | YES         | null              |
| competition_round  | text                     | YES         | null              |
| venue_type         | text                     | YES         | null              |
| date               | date                     | YES         | null              |
| place              | bigint                   | YES         | null              |
| com_trajectory_url | text                     | YES         | null              |
| attempt            | bigint                   | YES         | null              |
| wind_m_sec         | real                     | YES         | null              |
| video              | text                     | YES         | null              |

## JUMPLENS_AVG_CONTACT_AND_FLIGHT_LENGTH 

| column_name   | data_type                | is_nullable | column_default    |
| ------------- | ------------------------ | ----------- | ----------------- |
| id            | uuid                     | NO          | gen_random_uuid() |
| created_at    | timestamp with time zone | NO          | now()             |
| athlete_id    | character varying        | YES         | null              |
| LAST_Support  | double precision         | YES         | null              |
| STRI_Flight   | double precision         | YES         | null              |
| DE_Support    | double precision         | YES         | null              |
| HOP_Flight    | double precision         | YES         | null              |
| STEP_Support  | double precision         | YES         | null              |
| JUMP_Flight   | double precision         | YES         | null              |
| TOTAL_Support | double precision         | YES         | null              |
| TIME_Support  | double precision         | YES         | null              |
| TIME_Flight   | double precision         | YES         | null              |

## JUMPLENS_COMPETITIONS_DETAILS

| column_name      | data_type                | is_nullable | column_default    |
| ---------------- | ------------------------ | ----------- | ----------------- |
| id               | uuid                     | NO          | gen_random_uuid() |
| created_at       | timestamp with time zone | NO          | now()             |
| meeting_id       | bigint                   | NO          | null              |
| country          | text                     | YES         | null              |
| meeting_name     | text                     | YES         | null              |
| competition_type | text                     | YES         | null              |
| venue_type       | text                     | YES         | null              |
| date             | date                     | YES         | null              |
| logo             | text                     | YES         | null              |
| address          | text                     | YES         | null              |


##  JUMPLENS_COM_VELOCITY_CHANGES

| column_name        | data_type                | is_nullable | column_default    |
| ------------------ | ------------------------ | ----------- | ----------------- |
| id                 | uuid                     | NO          | gen_random_uuid() |
| created_at         | timestamp with time zone | NO          | now()             |
| athlete_id         | bigint                   | YES         | null              |
| HOP_DeltaUX_m_sec  | double precision         | YES         | null              |
| HOP_DeltaUY_m_sec  | double precision         | YES         | null              |
| STEP_DeltaUX_m_sec | double precision         | YES         | null              |
| STEP_DeltaUY_m_sec | double precision         | YES         | null              |
| JUMP_DeltaUX_m_sec | double precision         | YES         | null              |
| JUMP_DeltaUY_m_sec | double precision         | YES         | null              |
| meeting_id         | bigint                   | YES         | null              |

## JUMPLENS_PHASE_DISTANCES

| column_name        | data_type                | is_nullable | column_default    |
| ------------------ | ------------------------ | ----------- | ----------------- |
| created_at         | timestamp with time zone | NO          | now()             |
| id                 | uuid                     | NO          | gen_random_uuid() |
| meeting_id         | integer                  | YES         | null              |
| athlete_id         | bigint                   | YES         | null              |
| official_distance  | double precision         | YES         | null              |
| attempt            | bigint                   | YES         | null              |
| effective_distance | double precision         | YES         | null              |
| hop                | double precision         | YES         | null              |
| step               | double precision         | YES         | null              |
| jump               | double precision         | YES         | null              |
| hop_percent        | double precision         | YES         | null              |
| step_percent       | double precision         | YES         | null              |
| jump_percent       | double precision         | YES         | null              |
| technique          | text                     | YES         | null              |
| wind_m_sec         | double precision         | YES         | null              |
| event_type         | text                     | YES         | null              |
| competition_round  | text                     | YES         | null              |
| group              | text                     | YES         | null              |
| group_rank         | bigint                   | YES         | null              |
| status             | text                     | YES         | null              |

## JUMPLENS_TAKEOFF_VELOCITIES  

| column_name        | data_type                | is_nullable | column_default    |
| ------------------ | ------------------------ | ----------- | ----------------- |
| id                 | uuid                     | NO          | gen_random_uuid() |
| created_at         | timestamp with time zone | NO          | now()             |
| athlete_id         | bigint                   | YES         | null              |
| meeting_id         | bigint                   | YES         | null              |
| attempt            | bigint                   | YES         | null              |
| event_type         | text                     | YES         | null              |
| hop_ux             | double precision         | YES         | null              |
| hop_uy             | double precision         | YES         | null              |
| hop_angPr          | double precision         | YES         | null              |
| step_ux            | double precision         | YES         | null              |
| step_uy            | double precision         | YES         | null              |
| step_angPr         | double precision         | YES         | null              |
| jump_ux            | double precision         | YES         | null              |
| jump_uy            | double precision         | YES         | null              |
| jump_angPr         | double precision         | YES         | null              |
| effective_distance | double precision         | YES         | null              |
| official_distance  | double precision         | YES         | null              |


## JUMPLENS_LANDING_DISTANCE_VELOCITIES

| column_name | data_type                | is_nullable | column_default    |
| ----------- | ------------------------ | ----------- | ----------------- |
| id          | uuid                     | NO          | gen_random_uuid() |
| created_at  | timestamp with time zone | NO          | now()             |
| athlete_id  | character varying        | YES         | null              |
| HOP_STD     | double precision         | YES         | null              |
| HOP_UAX     | double precision         | YES         | null              |
| STEP_STD    | double precision         | YES         | null              |
| STEP_UAX    | double precision         | YES         | null              |
| JUMP_STD    | double precision         | YES         | null              |
| JUMP_UAX    | double precision         | YES         | null              |


## JUMPLENS_STRIDES_LENGTH    

| column_name          | data_type                | is_nullable | column_default    |
| -------------------- | ------------------------ | ----------- | ----------------- |
| id                   | uuid                     | NO          | gen_random_uuid() |
| created_at           | timestamp with time zone | NO          | now()             |
| athlete_id           | text                     | YES         | null              |
| FIRST_LANDING_STEP_m | double precision         | YES         | null              |
| HEIGHT_m             | double precision         | YES         | null              |
| UX_mps               | double precision         | YES         | null              |
| UY_mps               | double precision         | YES         | null              |


## Foreign Keys

```[
  {
    "table_name": "JUMPLENS_ATHLETES_PERFORMANCE",
    "column_name": "athlete_id",
    "foreign_table_name": "JUMPLENS_ATHLETES",
    "foreign_column_name": "athlete_id"
  },
  {
    "table_name": "JUMPLENS_ATHLETES_PERFORMANCE",
    "column_name": "meeting_id",
    "foreign_table_name": "JUMPLENS_COMPETITIONS_DETAILS",
    "foreign_column_name": "meeting_id"
  },
  {
    "table_name": "JUMPLENS_PHASE_DISTANCES",
    "column_name": "athlete_id",
    "foreign_table_name": "JUMPLENS_ATHLETES",
    "foreign_column_name": "athlete_id"
  },
  {
    "table_name": "JUMPLENS_PHASE_DISTANCES",
    "column_name": "meeting_id",
    "foreign_table_name": "JUMPLENS_COMPETITIONS_DETAILS",
    "foreign_column_name": "meeting_id"
  },
  {
    "table_name": "JUMPLENS_COM_VELOCITY_CHANGES",
    "column_name": "athlete_id",
    "foreign_table_name": "JUMPLENS_ATHLETES",
    "foreign_column_name": "athlete_id"
  },
  {
    "table_name": "JUMPLENS_AVG_CONTACT_AND_FLIGHT_LENGTH",
    "column_name": "athlete_id",
    "foreign_table_name": "JUMPLENS_ATHLETES",
    "foreign_column_name": "athlete_id"
  },
  {
    "table_name": "JUMPLENS_AVG_CONTACT_AND_FLIGHT_LENGTH",
    "column_name": "meeting_id",
    "foreign_table_name": "JUMPLENS_COMPETITIONS_DETAILS",
    "foreign_column_name": "meeting_id"
  },
  {
    "table_name": "JUMPLENS_COM_VELOCITY_CHANGES",
    "column_name": "meeting_id",
    "foreign_table_name": "JUMPLENS_COMPETITIONS_DETAILS",
    "foreign_column_name": "meeting_id"
  },
  {
    "table_name": "JUMPLENS_TAKEOFF_VELOCITIES",
    "column_name": "athlete_id",
    "foreign_table_name": "JUMPLENS_ATHLETES",
    "foreign_column_name": "athlete_id"
  },
  {
    "table_name": "JUMPLENS_TAKEOFF_VELOCITIES",
    "column_name": "meeting_id",
    "foreign_table_name": "JUMPLENS_COMPETITIONS_DETAILS",
    "foreign_column_name": "meeting_id"
  }
]```












