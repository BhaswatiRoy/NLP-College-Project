## Adding Operations

`operations` are no longer under `channels` in AsyncAPI Spec 3.0.0, instead, `operations` are separate objects in the AsyncAPI document on the same level. 
`channels` can be linked within `operations` by referencing them within the `channels`, just like the following example -

```
onUserSignUp:
  title: User sign up
  summary: Action to sign a user up.
  description: A longer description
  channel:
    $ref: '#/channels/userSignup'
```

Operations can be defined as an independent object in the AsyncAPI document. Operations have the following components for it's definition -

|  Field Name | Type | Description |
|---|---|---|
| title | string | an easy to understand headline for the operation |
| summary | string | a `ref` pointer |
| description | string | |
| Channel | Reference Object Link | |
| Action | "send" or "receive" | |
| Tags | Tag Object | |
| Bindings | Bindings Object | |
| Traits | Traits Object | |
| Bindings | Bindings Object | |

```
onUserSignUp:
  title: User sign up
  summary: Action to sign a user up.
  description: A longer description
  channel:
    $ref: '#/channels/userSignup'
  action: send
  tags:
    - name: user
    - name: signup
    - name: register
  bindings:
    amqp:
      ack: false
  traits:
    - $ref: '#/components/operationTraits/kafka'
```
