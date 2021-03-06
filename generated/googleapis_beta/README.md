Auto-generated Dart libraries for accessing [Google APIs][libs].

## Usage

First, obtain OAuth 2.0 access credentials. This can be done using the
`googleapis_auth` package. Your application can access APIs on behalf of a
user or using a service account.

After obtaining credentials, an API from the `googleapis` package can be
accessed with an authenticated HTTP client.

## Example

The following command line application lists files in Google Drive by using a
service account.

Create a `pubspec.yaml` file with the `googleapis_auth` and `googleapis`
dependencies.

```yaml
...
dependencies:
  googleapis: any
  googleapis_auth: any
```

Create a service account in the Google Cloud Console and save the credential
information.

Then create a Dart application to list files in a spececific project. *In the
example below, files from the `dart-on-cloud` project are listed.*

```dart
// bin/list_files.dart

import 'package:googleapis/storage/v1.dart';
import 'package:googleapis_auth/auth_io.dart';

final _credentials = new ServiceAccountCredentials.fromJson(r'''
{
  "private_key_id": ...,
  "private_key": ...,
  "client_email": ...,
  "client_id": ...,
  "type": "service_account"
}
''');

const _SCOPES = const [StorageApi.DevstorageReadOnlyScope];

void main() {
  clientViaServiceAccount(_credentials, _SCOPES).then((http_client) {
    var storage = new StorageApi(http_client);
    storage.buckets.list('dart-on-cloud').then((buckets) {
      print("Received ${buckets.items.length} bucket names:");
      for (var file in buckets.items) {
        print(file.name);
      }
    });
  });
}
```

[libs]: https://developers.google.com/discovery/libraries/

## Available Google APIs

The following is a list of APIs that are currently available inside this
package.

#### ![Logo](http://www.google.com/images/icons/product/search-16.gif) Ad Exchange Buyer API II - adexchangebuyer2 v2beta1

Accesses the latest features for managing Ad Exchange accounts, Real-Time Bidding configurations and auction metrics, and Marketplace programmatic deals.

Official API documentation: https://developers.google.com/ad-exchange/buyer-rest/reference/rest/

#### ![Logo](http://www.google.com/images/icons/product/search-16.gif) App Engine Admin API - appengine v1beta

The App Engine Admin API enables developers to provision and manage their App Engine applications.

Official API documentation: https://cloud.google.com/appengine/docs/admin-api/

#### ![Logo](http://www.google.com/images/icons/product/search-16.gif) App Engine Admin API - appengine v1beta4

The App Engine Admin API enables developers to provision and manage their App Engine applications.

Official API documentation: https://cloud.google.com/appengine/docs/admin-api/

#### ![Logo](http://www.google.com/images/icons/product/search-16.gif) App Engine Admin API - appengine v1beta5

The App Engine Admin API enables developers to provision and manage their App Engine applications.

Official API documentation: https://cloud.google.com/appengine/docs/admin-api/

#### ![Logo](http://www.google.com/images/icons/product/search-16.gif) Binary Authorization API - binaryauthorization v1beta1

The management interface for Binary Authorization, a system providing policy control for images deployed to Kubernetes Engine clusters.


Official API documentation: https://cloud.google.com/binary-authorization/

#### ![Logo](http://www.google.com/images/icons/product/search-16.gif) Stackdriver Error Reporting API - clouderrorreporting v1beta1

Groups and counts similar errors from cloud services and applications, reports new errors, and provides access to error groups and their associated errors.


Official API documentation: https://cloud.google.com/error-reporting/

#### ![Logo](http://www.google.com/images/icons/product/search-16.gif) Cloud Resource Manager API - cloudresourcemanager v1beta1

The Google Cloud Resource Manager API provides methods for creating, reading, and updating project metadata.

Official API documentation: https://cloud.google.com/resource-manager

#### ![Logo](http://www.google.com/images/icons/product/search-16.gif) Cloud Tasks API - cloudtasks v2beta2

Manages the execution of large numbers of distributed requests.

Official API documentation: https://cloud.google.com/tasks/

#### ![Logo](http://www.google.com/images/icons/product/search-16.gif) Dataflow API - dataflow v1b3

Manages Google Cloud Dataflow projects on Google Cloud Platform.

Official API documentation: https://cloud.google.com/dataflow

#### ![Logo](http://www.google.com/images/icons/product/search-16.gif) Dialogflow API - dialogflow v2beta1

An end-to-end development suite for conversational interfaces (e.g., chatbots, voice-powered apps and devices).

Official API documentation: https://cloud.google.com/dialogflow-enterprise/

#### ![Logo](https://www.gstatic.com/images/branding/product/1x/googleg_16dp.png) Google Cloud DNS API - dns v2beta1

Configures and serves authoritative DNS records.

Official API documentation: https://developers.google.com/cloud-dns

#### ![Logo](http://www.google.com/images/icons/product/search-16.gif) Cloud Identity-Aware Proxy API - iap v1beta1

Controls access to cloud applications running on Google Cloud Platform.

Official API documentation: https://cloud.google.com/iap

#### ![Logo](http://www.google.com/images/icons/product/search-16.gif) Cloud Natural Language API - language v1beta1

Provides natural language understanding technologies to developers. Examples include sentiment analysis, entity recognition, entity sentiment analysis, and text annotations.

Official API documentation: https://cloud.google.com/natural-language/

#### ![Logo](http://www.google.com/images/icons/product/search-16.gif) Cloud Natural Language API - language v1beta2

Provides natural language understanding technologies to developers. Examples include sentiment analysis, entity recognition, entity sentiment analysis, and text annotations.

Official API documentation: https://cloud.google.com/natural-language/

#### ![Logo](http://www.google.com/images/icons/product/search-16.gif) Stackdriver Logging API - logging v2beta1

Writes log entries and manages your Logging configuration.

Official API documentation: https://cloud.google.com/logging/docs/

#### ![Logo](http://www.google.com/images/icons/product/search-16.gif) Cloud OS Login API - oslogin v1alpha

Manages OS login configuration for Google account users.

Official API documentation: https://cloud.google.com/compute/docs/oslogin/rest/

#### ![Logo](http://www.google.com/images/icons/product/search-16.gif) Cloud OS Login API - oslogin v1beta

Manages OS login configuration for Google account users.

Official API documentation: https://cloud.google.com/compute/docs/oslogin/rest/

#### ![Logo](http://www.google.com/images/icons/product/search-16.gif) Proximity Beacon API - proximitybeacon v1beta1

Registers, manages, indexes, and searches beacons.

Official API documentation: https://developers.google.com/beacons/proximity/

#### ![Logo](http://www.google.com/images/icons/product/search-16.gif) Cloud Pub/Sub API - pubsub v1beta2

Provides reliable, many-to-many, asynchronous messaging between applications.


Official API documentation: https://cloud.google.com/pubsub/docs

#### ![Logo](http://www.google.com/images/icons/product/search-16.gif) Google Cloud Memorystore for Redis API - redis v1beta1

The Google Cloud Memorystore for Redis API is used for creating and managing Redis instances on the Google Cloud Platform.

Official API documentation: https://cloud.google.com/memorystore/docs/redis/

#### ![Logo](https://www.gstatic.com/images/branding/product/1x/googleg_16dp.png) Google Compute Engine Instance Group Updater API - replicapoolupdater v1beta1

[Deprecated. Please use compute.instanceGroupManagers.update method. replicapoolupdater API will be disabled after December 30th, 2016] Updates groups of Compute Engine instances.

Official API documentation: https://cloud.google.com/compute/docs/instance-groups/manager/#applying_rolling_updates_using_the_updater_service

#### ![Logo](http://www.google.com/images/icons/product/search-16.gif) Cloud Runtime Configuration API - runtimeconfig v1beta1

The Runtime Configurator allows you to dynamically configure and expose variables through Google Cloud Platform. In addition, you can also set Watchers and Waiters that will watch for changes to your data and return based on certain conditions.

Official API documentation: https://cloud.google.com/deployment-manager/runtime-configurator/

#### ![Logo](http://www.google.com/images/icons/product/search-16.gif) Cloud Speech API - speech v1beta1

Converts audio to text by applying powerful neural network models.

Official API documentation: https://cloud.google.com/speech-to-text/docs/quickstart-protocol

#### ![Logo](https://www.gstatic.com/images/branding/product/1x/googleg_16dp.png) Cloud SQL Admin API - sqladmin v1beta3

Cloud SQL provides the Cloud SQL Admin API, a REST API for administering your instances programmatically.

Official API documentation: https://cloud.google.com/sql/docs/reference/latest

#### ![Logo](https://www.gstatic.com/images/branding/product/1x/googleg_16dp.png) Cloud SQL Admin API - sqladmin v1beta4

Cloud SQL provides the Cloud SQL Admin API, a REST API for administering your instances programmatically.

Official API documentation: https://cloud.google.com/sql/docs/reference/latest

#### ![Logo](https://www.gstatic.com/images/branding/product/1x/googleg_16dp.png) Cloud Tool Results API - toolresults v1beta3

Reads and publishes results from Firebase Test Lab.

Official API documentation: https://firebase.google.com/docs/test-lab/

#### ![Logo](http://www.google.com/images/icons/product/search-16.gif) Cloud TPU API - tpu v1alpha1

TPU API provides customers with access to Google TPU technology.

Official API documentation: https://cloud.google.com/tpu/

#### ![Logo](http://www.google.com/images/icons/product/search-16.gif) Web Security Scanner API - websecurityscanner v1alpha

Web Security Scanner API (under development).

Official API documentation: https://cloud.google.com/security-scanner/

