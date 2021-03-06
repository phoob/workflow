# Events

Events can be used to extend the functionality of Workflow.

## Submission related events

### The `beforeSaveSubmission` event

Plugins can get notified before a submission is saved. Event handlers can prevent the submission from getting sent by setting `$event->isValid` to false.

```php
use verbb\workflow\elements\Submission;
use yii\base\Event;

Event::on(Submission::class, Submission::EVENT_BEFORE_SAVE, function(Event $e) {
    $submission = $event->sender;
    $event->isValid = false;
});
```

### The `afterSaveSubmission` event

Plugins can get notified after a submission has been saved

```php
use verbb\workflow\elements\Submission;
use yii\base\Event;

Event::on(Submission::class, Submission::EVENT_AFTER_SAVE, function(Event $e) {
    $submission = $event->sender;
});
```
