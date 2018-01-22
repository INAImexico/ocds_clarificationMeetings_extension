# Clarification Meetings
## Description:

In Mexico, it is mandatory to carry out at least one meeting of clarifications with voluntary assistance by the tenderers in order to answer questions related to the call for proposals or the modifications that have been made to it. These meetings are made in competitive procedures and are usually made before the period when the tender is open for submissions.
The "General technical guidelines for the publication, homologation and standardization of the information of the obligations established in the fifth title and in the fraction IV of article 31 of the General Law of Transparency and Access to Public Information, which must be disseminated by the subjects forced in the Internet portals and in the National Transparency Platform "(page 110), consider the mandatory publication of certain information related to clarification meetings.
In particular, the guidelines contemplate the publication of the following information:
- Date on which the clarification meeting was made
- Names of those attending the clarification meeting
- Names of the public servants attending the meeting of clarification
- Position occupied by the public servants attending the meeting of clarifications
Thus, with the aim of match the Open Contracting Data Standard (OCDS) with the transparency obligations in Mexico, and therefore, with the Transparency Obligations Portals System (SIPOT) administered by the National Institute of Transparency, Access to Information and Protection of Personal Data (INAI), we consider necessary to develop an extension that includes the information related to the clarification meetings.

## Proposal:

Add an array within the tender object. This array must contain the following values:

### Party Roles

- clarificationMeetingAttendee
- clarificationMeetingOfficial

### Schema

- Parties [array]
  - Organization {object}
    - position (Type: string, null)

- Tender {object}
  - clarificationMeetings [array]
    - clarificationMeeting {object}
      - id (Type: string, integer)
      - date  (format : date-time)(Type : string, null)
      - clarificationMeetingAttendees [array]
        - $ref : #/definitions/OrganizationReference
      - clarificationMeetingOfficials[array]
        - $ref : #/definitions/OrganizationReference

## Defining texts:

**Code** | **Title** | **Description**
--|--|--
position | Position | Position held by the official. This field is used to define the position occupied by the officials attending the clarification meeting.
clarificationMeetings | Clarification meetings | A list of the clarifications meetings related to the tender section.
clarificationMeeting | Clarification meeting | A clarification meeting is used to solve enquiries the tenderers may have about issues related to the call for proposals.
id | Meeting ID | A local identifier for this meeting, unique within this block.
date | Meeting date | The date on which the clarification meeting is held.
clarificationMeetingAttendees | Clarification meeting attendees | The tenderers or other actors attending the clarification meeting.
clarificationMeetingOfficials | Clarification meeting officials | The officials attending the clarification meeting.

## Issues 

Report issues for this extension in the [standard repository](https://github.com/open-contracting/standard/issues/621) of the Open Contracting Partnership.
