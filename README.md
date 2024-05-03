# Kratos test UI

Kratos version 1.1 

## Posibillity

- email, term of service, username are requried
- you should verify email, as a mail chatcher used mailslurper `localhost:4436`
- changing the password leads to automatical logout 
- changing the email leads to verification it
- you use kratos-admin-ui `localhost:8080` as admin tool

## Usage

To see what exactly return kratos use this code inside handler to logging the response:

```go
jsonUi, err := json.MarshalIndent(flow.Ui, "", "  ")
if err != nil {
    writeError(w, http.StatusInternalServerError, err)
    return
}
fmt.Printf("UI: \n%s\n", string(jsonUi))
```

`handleIndex` will return this in logs after you done email verification:

```text
Content-Length: 57
Content-Type: application/json
Ory-Webhook-Request-Id: 90f0fc1d-fa7a-4265-88a1-b8eaff54dbd6
User-Agent: Go-http-client/1.1
	//self-service-go    | [00]
{
   "user_id": "94d2ca3c-744b-491e-bcbd-b8e54843ce85"
}
```
