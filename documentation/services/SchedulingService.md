# SchedulingService

A list of all methods in the `SchedulingService` service. Click on the method name to view detailed information about that method.

| Methods                                                                     | Description |
| :-------------------------------------------------------------------------- | :---------- |
| [schedulingControllerScheduleMessage](#schedulingcontrollerschedulemessage) |             |
| [schedulingControllerRescheduleRun](#schedulingcontrollerreschedulerun)     |             |
| [schedulingControllerListRuns](#schedulingcontrollerlistruns)               |             |
| [schedulingControllerCancelRun](#schedulingcontrollercancelrun)             |             |
| [schedulingControllerRetryRun](#schedulingcontrollerretryrun)               |             |
| [schedulingControllerReplayRun](#schedulingcontrollerreplayrun)             |             |

## schedulingControllerScheduleMessage

- HTTP Method: `POST`
- Endpoint: `/api/schedule-message`

**Parameters**

| Name | Type                                                  | Required | Description       |
| :--- | :---------------------------------------------------- | :------- | :---------------- |
| body | [ScheduleMessageDto](../models/ScheduleMessageDto.md) | ✅       | The request body. |

**Example Usage Code Snippet**

```typescript
import { MessageBodyDto, ScheduleMessageDto, TriochatSdk } from '@triochat/@triochat/triochat-sdk';

(async () => {
  const triochatSdk = new TriochatSdk({});

  const messageDto: MessageDto = {
    messageType: 'messageType',
    messageText: 'messageText',
    components: ['components'],
    templateName: 'template_name',
  };

  const messageBodyDto: MessageBodyDto = {
    segmentIds: ['segment_ids'],
    allLeads: true,
    message: messageDto,
  };

  const scheduleMessageDto: ScheduleMessageDto = {
    messageBody: messageBodyDto,
    token: 'token',
    messageDelay: 'messageDelay',
    userId: 'userId',
    campaignName: 'campaignName',
    campaignDescription: 'campaignDescription',
    campaignGoals: ['campaignGoals'],
    segmentName: 'segmentName',
  };

  const { data } = await triochatSdk.scheduling.schedulingControllerScheduleMessage(scheduleMessageDto);

  console.log(data);
})();
```

## schedulingControllerRescheduleRun

- HTTP Method: `PUT`
- Endpoint: `/api/reschedule-run`

**Parameters**

| Name     | Type   | Required | Description |
| :------- | :----- | :------- | :---------- |
| runId    | string | ✅       |             |
| newDelay | string | ✅       |             |

**Example Usage Code Snippet**

```typescript
import { TriochatSdk } from '@triochat/@triochat/triochat-sdk';

(async () => {
  const triochatSdk = new TriochatSdk({});

  const { data } = await triochatSdk.scheduling.schedulingControllerRescheduleRun({
    runId: 'runId',
    newDelay: 'newDelay',
  });

  console.log(data);
})();
```

## schedulingControllerListRuns

- HTTP Method: `GET`
- Endpoint: `/api/list-runs`

**Parameters**

| Name            | Type                                | Required | Description |
| :-------------- | :---------------------------------- | :------- | :---------- |
| userId          | string                              | ✅       |             |
| page            | number                              | ❌       |             |
| pageSize        | number                              | ❌       |             |
| status          | [Status[]](../models/Status.md)     | ❌       |             |
| dateRange       | [DateRange](../models/DateRange.md) | ❌       |             |
| searchQuery     | string                              | ❌       |             |
| customDateRange | any                                 | ❌       |             |

**Example Usage Code Snippet**

```typescript
import { TriochatSdk } from '@triochat/@triochat/triochat-sdk';

(async () => {
  const triochatSdk = new TriochatSdk({});

  const dateRange = DateRange.LAST_7_DAYS;

  const { data } = await triochatSdk.scheduling.schedulingControllerListRuns({
    userId: 'userId',
    page: 1,
    pageSize: 10,
    status: [status],
    dateRange: dateRange,
    searchQuery: 'searchQuery',
    customDateRange: {},
  });

  console.log(data);
})();
```

## schedulingControllerCancelRun

- HTTP Method: `DELETE`
- Endpoint: `/api/cancel-run`

**Parameters**

| Name  | Type   | Required | Description |
| :---- | :----- | :------- | :---------- |
| runId | string | ✅       |             |

**Example Usage Code Snippet**

```typescript
import { TriochatSdk } from '@triochat/@triochat/triochat-sdk';

(async () => {
  const triochatSdk = new TriochatSdk({});

  const { data } = await triochatSdk.scheduling.schedulingControllerCancelRun({
    runId: 'runId',
  });

  console.log(data);
})();
```

## schedulingControllerRetryRun

- HTTP Method: `GET`
- Endpoint: `/api/retry-run`

**Parameters**

| Name  | Type   | Required | Description |
| :---- | :----- | :------- | :---------- |
| runId | string | ✅       |             |

**Example Usage Code Snippet**

```typescript
import { TriochatSdk } from '@triochat/@triochat/triochat-sdk';

(async () => {
  const triochatSdk = new TriochatSdk({});

  const { data } = await triochatSdk.scheduling.schedulingControllerRetryRun({
    runId: 'runId',
  });

  console.log(data);
})();
```

## schedulingControllerReplayRun

- HTTP Method: `POST`
- Endpoint: `/api/replay-run`

**Parameters**

| Name | Type                                      | Required | Description       |
| :--- | :---------------------------------------- | :------- | :---------------- |
| body | [ReplayRunDto](../models/ReplayRunDto.md) | ✅       | The request body. |

**Example Usage Code Snippet**

```typescript
import { ReplayRunDto, TriochatSdk } from '@triochat/@triochat/triochat-sdk';

(async () => {
  const triochatSdk = new TriochatSdk({});

  const replayRunDto: ReplayRunDto = {
    runId: 'runId',
  };

  const { data } = await triochatSdk.scheduling.schedulingControllerReplayRun(replayRunDto);

  console.log(data);
})();
```

<!-- This file was generated by liblab | https://liblab.com/ -->
