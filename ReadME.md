
# Enforcing Mandatory Fields Using UI Policies and Migrating Changes with Update Sets

## Project Overview

This project demonstrates how to enforce mandatory fields dynamically in ServiceNow using **UI Policies and UI Policy Actions**. The mandatory requirement of specific fields changes based on the selected Incident Category or Priority.

The project also demonstrates the use of **Local Update Sets** to capture and manage configuration changes made in ServiceNow.

## Objectives

- Implement conditional mandatory fields using UI Policies.
- Configure UI Policy Actions for specific Incident fields.
- Improve the accuracy of information entered while creating incidents.
- Test the mandatory-field behaviour under different conditions.
- Capture configuration changes using Local Update Sets.

## Technologies Used

- **Platform:** ServiceNow
- **Release:** Australia Release
- **Application:** Incident Management
- **Table:** Incident `[incident]`
- **Features:** UI Policies, UI Policy Actions, Local Update Sets

## Implemented UI Policies

Four UI Policies were created and configured on the Incident table.

| UI Policy | Condition | Mandatory Field |
|---|---|---|
| Hardware - Configuration Item Mandatory | Category = Hardware | Configuration Item (`cmdb_ci`) |
| Software - Business Service Mandatory | Category = Software | Service (`business_service`) |
| Network - Assignment Group Mandatory | Category = Network | Assignment Group (`assignment_group`) |
| Critical Priority - Description Mandatory | Priority = 1 - Critical | Description (`description`) |

### UI Policy Configuration

The following settings were enabled for all four UI Policies:

- Active: True
- On Load: True
- Reverse if False: True

The corresponding UI Policy Actions were configured to make the required fields mandatory.

## Implementation

### 1. Hardware Category

When the Incident Category is selected as Hardware, the Configuration Item field becomes mandatory.

### 2. Software Category

When the Incident Category is selected as Software, the Service field becomes mandatory.

### 3. Network Category

When the Incident Category is selected as Network, the Assignment Group field becomes mandatory.

### 4. Critical Priority

When the Incident Priority becomes Critical, the Description field becomes mandatory.

## Testing and Results

All four UI Policies were tested using the Incident form.

| Test Scenario | Expected Result | Observed Result |
|---|---|---|
| Hardware Category | Configuration Item becomes mandatory | Successful |
| Software Category | Service becomes mandatory | Successful |
| Network Category | Assignment Group becomes mandatory | Successful |
| Critical Priority | Description becomes mandatory | Successful |

The tests confirmed that the corresponding mandatory indicators appeared on the Incident form when the configured conditions were satisfied.

## Update Set Management

A Local Update Set was created to capture the configuration changes.

**Update Set Details:**

- Name: `Mandatory_Fields_UI_Policies_Project`
- Application: Global
- Final State: Complete
- Customer Updates: 11 records observed

The Customer Updates list included the four UI Policies and their four corresponding UI Policy Actions.

Update Sets provide a method to transfer configuration changes between ServiceNow instances. The general migration workflow includes completing the source Update Set, exporting it as XML, importing it into a target instance, previewing the changes, resolving conflicts, and committing the changes.


## Conclusion

This project successfully demonstrates conditional mandatory-field enforcement using ServiceNow UI Policies. Four different conditions were implemented and tested on the Incident form.

The project also provided practical experience in managing configuration changes through Local Update Sets.

## Team Members

| Name | Registration Number |
|---|---|
| Sreekar Sai Arveti | AP24110011234 |
| Venkat Y | AP24110011911 |
| Surya Vardhan Ch | AP24110011239 |
| Teja Tarun Ch | AP24110011907 |

## Academic Information

**University:** SRM University AP  
**Programme:** B.Tech  
**Project Domain:** ServiceNow  
**Faculty Guide:** Add Faculty Name  
