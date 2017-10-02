# Email Validation Rules
This is a collection of mailbox validation rules for well-known email services.

## `domain-aliases.csv`
Contains a list of domain aliases that will deliver to the same mailbox. The `source` domain will be rewritten to the `target` during the delivery.
For example, Google has a domain alias, so `john.doe@googlemail.com` will become `john.doe@gmail.com`.

## `vendors.csv`
Domains are grupped by vendors. This is to apply same rule(s) to different domains.

## `mailbox-canonicals.csv`
Each `search` and `replace` rule (regular expression) is applied to the mailbox to form a "real" (non-disposable) mailbox (username).
For example, Google is allowing `.` (dot) and `+tag` as a decorator, i.e. `john.doe+jane.doe@gmail.com` is just a decorated name for `johndoe@gmail.com` mailbox.

## `mailbox-rules.csv`
A list of vendor rules applied to the mailbox during delivery (after cleaning up the decorations, see `mailbox-canonicals.csv` section above).
Mailbox should match the regular expression rule to succeed, unless it's marked as `inverted`.
`Comment` field could be used to form a human-readable error message during the validation.
