---
title: XS - Precondition
---

# <img src="../assets/docuBadge (11).png" alt="" data-size="line"> Precondition <a href="#xs-precondition" id="xs-precondition"></a>

```javascript
precondition if ("a" == 1) {
  error_type = "notfound"
  error = "Error message to return"
  payload = "Payload"
}
```

| Parameter   | Purpose                                   | Example                                        |
| ----------- | ----------------------------------------- | ---------------------------------------------- |
| error\_type | The type of error to throw                | `"notfound"`, `"forbidden"`, `"invalid"`       |
| error       | The error message to display              | `"Resource not found"`, `"Access denied"`      |
| payload     | Additional data to include with the error | `"Error details"`, `{reason: "Invalid input"}` |

<details>

<summary>Example</summary>

```javascript
precondition if ($user.role != "admin") {
  error_type = "forbidden"
  error = "Admin access required"
  payload = {
    required_role: "admin",
    current_role: $user.role
  }
}
```

* Checks a condition and throws an error if the condition is true
* Allows specifying error type, message, and additional payload
* Useful for validation and access control
* Stops execution if condition is met

</details>
