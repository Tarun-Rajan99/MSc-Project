## Column Types

**time**: seconds elapsed since an arbitrary start point.

**source user & destination user**: The source user is the idenitity initiating the request and the destination user is the account user on the target machine

**source computer & destination computer**: The physical machines involved, the source computer is where the request originates and the destination computer is the target being authenticated against.

**authentication type**: the protocol used i.e Kerberos can be considered standard domain authenticaiton

**logon type**: How the logon happened

**authentication orientation**: What kind of event

**Outcome**: What it success or failure




- The dataset is 58 days, which is approximately 5 million seconds.
- There are human users, machine users (indicated with $), anonymous window session, and other processes (e.g network services)
- Failed authentication events are only included for users that had a successful authentication event somewhere within the data set.


## What I want to gauge from the EDA:

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
