# Count Passing Time

UPDATE: 
Time.time does not work when reloading the current scene, for example you get hit by an obstacle and press play again and reload the scene, the timer will not reset.  Can use Time.delta time to correctly handle this

```c#
    Float elapsed = 0f;

    elapsed += Time.deltaTime;

    float seconds = Mathf.Floor(elapsed) % 60;
    float fMinutes = elapsed / 60;
    float minutes = Mathf.Floor(fMinutes) % 60;
    float fHours = fMinutes / 60;
    float hours = Mathf.Floor(fHours) % 60;

    string timerText = string.Format("{0}:{1}:{2}",
        hours.ToString("00"),
        minutes.ToString("00"),
        seconds.ToString("00")
    );

    gameTimer.SetText(timerText);
```


Original:
Use Time.time to get the time of the current frame and add that to a starting 0f to get elapsed time.

!Note: Timescale and max delta time settings will effect this

```c#
Float elapsed = 0f;

Update() {
    elapsed += Time.time;

    float seconds = Mathf.Floor(elapsed) % 60;
    elapsed = elapsed / 60;
    float minutes = Mathf.Floor(elapsed) % 60;
    elapsed = elapsed / 60;
    float hours = Mathf.Floor(elapsed) % 60;

    string timerText = string.Format("{0}:{1}:{2}",
        hours.ToString("00"),
        minutes.ToString("00"),
        seconds.ToString("00")
    );
}
```

---
Back Links

* [Time](../0_time.md)
