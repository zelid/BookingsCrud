# ServiceStack Stack Overflow on self-referenced models demo

Using self-referenced models in recent ServiceStack versions produces stack-overflow exception on accessing AutoQuery metadata.
Looks like the issue is related to a recent changes for AutoCRUD support. Some longer time ago (before AutoCRUD) it used to work.

# Steps to reproduce:

1. Reference this class as a property to Booking DB model:

```
public class MenuItem
{
    public string Title { get; set; }
    public string Url { get; set; }
    public List<MenuItem> Children { get; set; }
}
```

2. Try to open:
https://localhost:5001/autoquery/metadata


