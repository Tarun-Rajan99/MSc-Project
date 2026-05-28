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


Failed authentication events are only included for users that had a successful authentication event somewhere within the data element.




<img width="300" height="300" alt="Screenshot 2026-05-27 at 12 35 36" src="https://github.com/user-attachments/assets/cd34932d-b0cf-4bd3-bb71-db5d78c05753" />

---

## What I want to gauge from the EDA:

My EDA:

Event Count: 1051430459

Distinct src human users:  30,342
Distinct dest human users: 30,801
Union (src ∪ dest):        32,116

Distinct src machine accounts:  17,586
Distinct dest machine accounts: 17,517
Union (src ∪ dest):             17,606

Distinct source computers:      16,230
Distinct destination computers: 15,895
Distinct computers (union):     17,666


Source user percentages:
Machine 60.2%
Users 32.5%
Other 7.28%


<img width="300" height="254" alt="Screenshot 2026-05-28 at 15 31 16" src="https://github.com/user-attachments/assets/03f72202-d731-46e1-8f2a-3d34c6937f7d" />




- Total auths for each user
- Number of distinct dest_comp per user — how many machines does each user touch?
- The distribution of authentication events over time (how machines and users differ)
- Failure rates per user
- Temporal patterns

**Goal**: To build a feature vector that will model what normality / what features differentiate users
