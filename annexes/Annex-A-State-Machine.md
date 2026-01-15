

\# Annex A — Appeal–Termination Ordering Formalization (State Machine)



┌─────────────────────────────────────────────────────────────────┐

│                    9DA AGI/ASI Execution State Machine          │

└─────────────────────────────────────────────────────────────────┘



States (Exclusive):

• MANDATE\_DEFINED

• APPEAL\_WINDOW

• AUTHORIZED

• DENIED

• EXECUTING

• TERMINATING

• ARCHIVED



Transitions:



\[MANDATE\_DEFINED]

&nbsp;   ├→ \[APPEAL\_WINDOW]

&nbsp;   └→ \[AUTHORIZED]



\[APPEAL\_WINDOW]

&nbsp;   ├→ \[AUTHORIZED]

&nbsp;   ├→ \[DENIED]

&nbsp;   └→ \[TERMINATING]



\[AUTHORIZED]

&nbsp;   ├→ \[EXECUTING]

&nbsp;   └→ \[TERMINATING]



\[DENIED]

&nbsp;   └→ \[TERMINATING]



\[EXECUTING]

&nbsp;   └→ \[TERMINATING]



\[TERMINATING]

&nbsp;   └→ \[ARCHIVED]



Critical Invariants:

1\. Termination time immutable

2\. Termination has priority over all states

3\. Termination is non-appealable

4\. Execution has one exit only

5\. Archive is silent and terminal





