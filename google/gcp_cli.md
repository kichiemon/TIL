# Install

./google-cloud-sdk/install.sh
Welcome to the Google Cloud SDK!

To help improve the quality of this product, we collect anonymized usage data
and anonymized stacktraces when crashes are encountered; additional information
is available at <https://cloud.google.com/sdk/usage-statistics>. You may choose
to opt out of this collection now (by choosing 'N' at the below prompt), or at
any time in the future by running the following command:

    gcloud config set disable_usage_reporting true

Do you want to help improve the Google Cloud SDK (Y/n)?  Y


Your current Cloud SDK version is: 245.0.0
The latest available version is: 255.0.0

┌───────────────────────────────────────────────────────────────────────────────────────────────────────────────┐
│                                                   Components                                                  │
├──────────────────┬──────────────────────────────────────────────────────┬──────────────────────────┬──────────┤
│      Status      │                         Name                         │            ID            │   Size   │
├──────────────────┼──────────────────────────────────────────────────────┼──────────────────────────┼──────────┤
│ Update Available │ BigQuery Command Line Tool                           │ bq                       │  < 1 MiB │
│ Update Available │ Cloud SDK Core Libraries                             │ core                     │ 11.2 MiB │
│ Update Available │ Cloud Storage Command Line Tool                      │ gsutil                   │  3.6 MiB │
│ Not Installed    │ App Engine Go Extensions                             │ app-engine-go            │ 56.4 MiB │
│ Not Installed    │ Cloud Bigtable Command Line Tool                     │ cbt                      │  6.3 MiB │
│ Not Installed    │ Cloud Bigtable Emulator                              │ bigtable                 │  6.6 MiB │
│ Not Installed    │ Cloud Datalab Command Line Tool                      │ datalab                  │  < 1 MiB │
│ Not Installed    │ Cloud Datastore Emulator                             │ cloud-datastore-emulator │ 18.4 MiB │
│ Not Installed    │ Cloud Datastore Emulator (Legacy)                    │ gcd-emulator             │ 38.1 MiB │
│ Not Installed    │ Cloud Firestore Emulator                             │ cloud-firestore-emulator │ 35.9 MiB │
│ Not Installed    │ Cloud Pub/Sub Emulator                               │ pubsub-emulator          │ 34.8 MiB │
│ Not Installed    │ Cloud SQL Proxy                                      │ cloud_sql_proxy          │  3.7 MiB │
│ Not Installed    │ Emulator Reverse Proxy                               │ emulator-reverse-proxy   │ 14.5 MiB │
│ Not Installed    │ Google Cloud Build Local Builder                     │ cloud-build-local        │  5.9 MiB │
│ Not Installed    │ Google Container Registry's Docker credential helper │ docker-credential-gcr    │  1.8 MiB │
│ Not Installed    │ gcloud Alpha Commands                                │ alpha                    │  < 1 MiB │
│ Not Installed    │ gcloud Beta Commands                                 │ beta                     │  < 1 MiB │
│ Not Installed    │ gcloud app Java Extensions                           │ app-engine-java          │ 85.9 MiB │
│ Not Installed    │ gcloud app PHP Extensions                            │ app-engine-php           │ 21.9 MiB │
│ Not Installed    │ gcloud app Python Extensions                         │ app-engine-python        │  6.0 MiB │
│ Not Installed    │ gcloud app Python Extensions (Extra Libraries)       │ app-engine-python-extras │ 28.5 MiB │
│ Not Installed    │ kubectl                                              │ kubectl                  │  < 1 MiB │
└──────────────────┴──────────────────────────────────────────────────────┴──────────────────────────┴──────────┘
To install or remove components at your current SDK version [245.0.0], run:
  $ gcloud components install COMPONENT_ID
  $ gcloud components remove COMPONENT_ID

To update your SDK installation to the latest version [255.0.0], run:
  $ gcloud components update



To take a quick anonymous survey, run:
  $ gcloud alpha survey


Modify profile to update your $PATH and enable shell command
completion?

Do you want to continue (Y/n)?  Y

The Google Cloud SDK installer will now prompt you to update an rc
file to bring the Google Cloud CLIs into your environment.

Enter a path to an rc file to update, or leave blank to use
[/Users/ikuya/.config/fish/config.fish]:
Backing up [/Users/ikuya/.config/fish/config.fish] to [/Users/ikuya/.config/fish/config.fish.backup].
[/Users/ikuya/.config/fish/config.fish] has been updated.

==> Start a new shell for the changes to take effect.


For more information on how to get started, please visit:
  https://cloud.google.com/sdk/docs/quickstarts


