# Communications

Tracking all correspondence with authorities, allies, and stakeholders. Every letter sent and every response received is logged here for transparency.

## Structure

```
foi/
  requests/        # Copies of FOI requests sent
  responses/       # Responses received (date-prefixed)
  tracker.md       # Status tracker for all FOI requests

authorities/       # One subfolder per authority
  royal-parks/     # The Royal Parks charity
  westminster-council/  # Westminster City Council
  dcms/            # Dept for Culture, Media and Sport
  historic-england/    # Heritage statutory consultee

allies/            # Organisations we're building relationships with
  london-national-park-city/
  new-london-architecture/
  create-streets/

templates/         # Reusable letter/email templates
  foi-template.md
  councillor-letter.md
  ally-intro-email.md
  press-pitch.md
```

## Logging Convention

Each subfolder contains markdown files named with the date and a short description:

```
2026-03-15_foi-request-concession-details.md
2026-04-10_foi-response-partial.md
2026-04-12_follow-up-request.md
```

Each file should contain:

* Date sent/received
* From / To
* Subject
* Full text (or summary + link to PDF for scanned documents)
* Status (sent / awaiting response / responded / escalated)
* Next action

## Privacy

* Do not commit personal email addresses, phone numbers, or home addresses of individuals
* Public officials' professional contact details (available on gov.uk or official websites) are fine
* FOI responses are public documents and can be committed in full
* Redact any personal data of third parties before committing
