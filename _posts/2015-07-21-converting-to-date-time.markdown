---
published: true
title: Date time woes
layout: post
---
I spent about 2 hours today, just trying to convert string representations of date time into other representations. What are the odds.

The job is the same:

1. Take some string representation of a date and time and convert into a date time object in the programming language of choice,
2. Apply a timezone to that date time object
3. Spit out another string representation, now shifted according to the applied timezone

Sounds easy enough. I must be getting slow. It took too long.

In Python:

```
def convert_unix_to_utc_string(unix_timestamp):
  local_tz = tz.tzlocal()
  # The unix timestamp is in UTC.
  # Python presents it in the local timezone. So we have to call
  # astimezone to convert it back to UTC.

  # Naive datetime, needs a timezone
  # Replace with local timezone
  # Then convert to utc timezone
  as_utc_datetime = datetime.datetime.fromtimestamp(unix_timestamp)\
          .replace(tzinfo=tz.tzlocal())\
          .astimezone(pytz.utc)
  # Now return the string version of this
  return as_utc_datetime.strftime('%Y-%m-%d %H:%M:%S UTC')
```

In Swift:

```
        if let createdAt : String = someCreatedAtObject as? String {

            let dateFormatter = NSDateFormatter()
            dateFormatter.dateFormat = "yyyy-MM-dd'T'HH:mm:ss.SS'Z'" // Read using iso-8601 format
            // The date given to us is in UTC...
            dateFormatter.timeZone = NSTimeZone(name: "UTC")
            if let createdAtDate  = dateFormatter.dateFromString(createdAt) where createdAt != "" {
            
                // ... but we want to display it in local understandable time
                dateFormatter.dateFormat = "dd MMM yyyy, hh:mm a"
                dateFormatter.timeZone = NSTimeZone.localTimeZone()
                self.createdAtLabel?.text = dateFormatter.stringFromDate(createdAtDate)
            }

```

But it was pretty illuminating. It is always going to be hard to remember what you are doing if you're only doing it once per project. And since there are non-standard ways to do these conversions.