# OPTIMAL PROJECT LOCATION SUGGESTION USING REGION WISE EMPLOYEE PROFICIENCY

This business network defines:

**Participants**
`Facilitator` `Trainer` 

**Assets**
`Course` `Cerificate` 

**Transactions**
`CreateDemoTransaction` `IssueCertificate` `ValidateCertificate`

To test this Business Network Definition in the **Test** tab:

Submit a `CreateDemoTransaction` transaction:

```
{
  "$class": "org.skill.CreateDemoTransaction"
}
```

This transaction populates the Participant Registries with a `Facilitator`, an `Trainer`. The Asset Registries will have a `Course` asset, `Certificate` asset.

Submit a `IssueCertificate` transaction:

```
{
  "$class": "org.skill.IssueCertificate",
  "courseId": "",
  "courseName": "GWPC",
  "course": {
    "$class": "org.skill.Course",
    "contractId": "7432",
    "courseId": "",
    "courseName": "GWPC",
    "resource": [],
    "facilitator": "resource:org.skill.Facilitator#0173",
    "trainer": "resource:org.skill.Trainer#0202",
    "skillDateTime": "2018-05-25T11:21:12.721Z"
  }
}
```

Creates the course and ceritificate is issued.

Submit a `ValidateCertificate` transaction for `CT_02` to validate the resource ceritificate, based on the parameters of the `CT_02` certificate contract:

```
{
  "$class": "org.skill.ValidateCertificate",
  "resourceName": "",
  "certificateNumber": "",
  "certificate": "resource:org.skill.Certificate#CT_02"
}
```

If the resource data is valid, skill is added to the database.

