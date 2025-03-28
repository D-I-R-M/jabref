# Journal Abbreviations

## Preparation

- Ensure that `buildres/abbrv.jabref.org` contains data. Otherwise, the submodules were not configured correctly.
- Ensure that `build/resources/main/journals/journal-list.mv` exists. It is generated by gradle task `generateJournalListMV`, which uses `org.jabref.cli.JournalListMvGenerator`.

## Where does the data come from?

The generator uses all `.csv` files from <https://github.com/JabRef/abbrv.jabref.org/tree/main/journals>, but ignores following ones:

```java
        Set<String> ignoredNames = Set.of(
                // remove all lists without dot in them:
                // we use abbreviation lists containing dots in them only (to be consistent)
                "journal_abbreviations_entrez.csv",
                "journal_abbreviations_medicus.csv",
                "journal_abbreviations_webofscience-dotless.csv",

                // we currently do not have good support for BibTeX strings
                "journal_abbreviations_ieee_strings.csv"
        );
```

## Future work

See <https://github.com/JabRef/jabref-issue-melting-pot/issues/41>
