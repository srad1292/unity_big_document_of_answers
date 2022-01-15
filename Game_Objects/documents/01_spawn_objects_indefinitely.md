# Spawn Objects Indefinitely

To spawn objects indefinitely, we need a coroutine that uses a while(true) with some delay inside the while loop and then the instantiation

```c#
public IEnumerator SpawnObstacle() {
    while (true) {
        yield return new WaitForSeconds(spawnDelay);
        Obstacle obstacle = Instantiate(obstaclePrefab, transform.position, Quaternion.identity);
        obstacle.SetObstacleMoveSpeed(obstacleMoveSpeed);
    }
}
```

We can also have a variable as the condition which we can toggle off somewhere else to turn off the coroutine  

```c#
void TurnOnSpawning() {
    StartCoroutine(SpawnObstacle());
}

IEnumerator SpawnObstacle() {
    while (spawnObstacles) {
        yield return new WaitForSeconds(spawnDelay);
        Obstacle obstacle = Instantiate(obstaclePrefab, transform.position, Quaternion.identity);
        obstacle.SetObstacleMoveSpeed(obstacleMoveSpeed);
    }
}

void TurnOffSpawning() {
    StartCoroutine(StopSpawningAfterDelay(stopSpawningDelay));
}

IEnumerator StopSpawningAfterDelay(float seconds) {
    yield return new WaitForSeconds(seconds);
    StopSpawning();
}

void StopSpawning() {
    spawnObstacles = false;
}
```

---
Back Links

* [Game Objects](../0_game_objects.md)
