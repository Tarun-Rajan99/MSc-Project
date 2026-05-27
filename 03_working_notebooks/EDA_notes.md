A. D. Kent. Cyber-security data sources for dynamic network research. In N. M. Adams
and N. A. Heard, editors, Dynamic networks and cyber-security, chapter 2, pages 37–64.
World Scientific, 2016. [https://ebookcentral.proquest.com/lib/imperial/reader.action?docID=4528809&c=UERG&ppg=53]

- Time: The time of the authentication event
- SourceUser@Domain: The user initiating the authentication event. If the user ends in '$', then it is a computer account for the specified computer. Domain is either DOMx, indicating an Active Directory domain or Cx, indicating a local computer account on computer Cx.
- Destination User@Domain: The user that the authentication event is mapping to. In many cases, this user will be the same as the Source User, but in other cases this is an authentication mapping event where Source User becomes (or attempts to become) the Destination User. User and domain details are the same as discussed for Source Users.
- Source Computer : The computer originating the authentication event.
- Destination Computer : The computer that the authentication event is terminating at. In many cases the Destination Computer is the same as the Source Computer, indicating a local authentication event on the computer. If they are different, it indicates an authentication event where the user is authenticating from one computer to another; in other words the user is moving through the network. Destination Computer in some instances is the special cases of a ticket granting ticket TGT or a user identity. These are speciﬁc to Kerberos service ticket (TGS) requests where the Source User is requesting either a new TGT or a TGS speciﬁc to a user account for various services that may be owned (run) by that user account (generally used by automated accounts and services).
- Authentication Type : This indicates the type of authentication occurring including Negotiate (a general type commonly seen), Kerberos and NTLM. Several other types occur as well. In some instances, the authentication type is not indicated and is represented with a question mark.
Logon Type : The type of authentication occurring including across the Network, an Interactive keyboard session, a Batch event, a system Service, a screen saver Lock or Unlock and several others. In some instances, the Logon Type cannot be determined or speciﬁed and is represented with a question mark.
- Authentication Orientation : How the authentication event is being used. This includes indicating whether it is for granting a Kerberos TGT or TGS, a log on or log off event, or an authentication credential mapping. In some instances, the Authentication Orientation cannot be determined and is represented with a question mark.
- Success or Failure : Indicating whether the authentication event was successfully completed or failed. Failure could happen for several reasons including the wrong password was provided, a locked out account, or an authorisation failure.


**Event Count** : 1,051,430,459
**User Count**: 12,418
**Computer Count**: 17,666


---


## What I want to gauge from the EDA:


- The distribution of authentication events over time (how machines and users differ)
- 

-----


For clustering on auth data, your EDA should build towards understanding what features will differentiate users. Here's what to focus on:
Volume features

Total auth events per user
Auth events per time window (hourly/daily) — establishes normal behaviour baseline
Are some users way more active than others?

Failure behaviour

Failure rate per user (failures / total)
Users with unusually high failure rates — could be attackers or just locked accounts
Failures followed quickly by a success — classic brute force pattern

Diversity features

Number of distinct dest_comp per user — how many machines does each user touch?
Number of distinct dest_user — are they authenticating as multiple identities?
Users accessing many machines are interesting for lateral movement detection

Protocol behaviour

NTLM vs Kerberos ratio per user — heavy NTLM usage is suspicious
Do certain users switch protocols abnormally?

Temporal patterns

When does each user typically authenticate? Day/night?
Are there users active outside business hours?
Sudden spikes in activity

Anomalous patterns specifically relevant to red team

src_user ≠ dest_user events per user
src_comp ≠ dest_comp on machine accounts (machine authenticating from wrong machine)
New dest_comp never seen before for that user

Practical EDA order:

Basic counts and distributions first
Per-user aggregations
Temporal patterns
Flag the anomalous patterns above
Then check against redteam.txt.gz to see if your flags line up with known attacks

The goal is to end up with a feature vector per user that captures their "normal" behaviour — clustering will then naturally group similar users and isolate outliers.
