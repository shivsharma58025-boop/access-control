# access-control

## Name entry and shared saving

Names can be submitted with the phone keyboard's Enter/Go key or the Add button. Without a configured database, names are saved only in that browser and the page displays a local-only status.

To enable sharing between devices, create a Firebase Realtime Database and set `DB` in the shared-sync section of `index.html` to its database URL (without a trailing slash). The page stores each authorization as an individual record under `/auth/<module-index>/`, so simultaneous additions do not replace one another. It refreshes shared lists every eight seconds.

The page currently has no user authentication. Do not enable unrestricted public database read/write rules for real employee data; use an authenticated backend or add Firebase Authentication and restrict database rules before deploying. The existing built-in names are copied to the database the first time it is empty.