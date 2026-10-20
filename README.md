# Void Client

Deobfuscated 634 2010-12-14 client

# Build

Build the client with Gradle, no install needed:

```gradle
./gradlew shadowJar
```

You will find the built `void-client.jar` in `/client/build/libs`.

If you're having issues with OpenGL/DirectX make sure you're using or running with a 32bit jre.

```bash
java -jar void-client.jar -d32
```

# Lobby

The client opens the native lobby by default. Use a server with revision 634 lobby login support. Select a world and Play to enter the game; Exit to lobby returns to the lobby, and Exit to login signs out.

```bash
java -jar client/build/libs/void-client-1.2.0.jar --address 127.0.0.1 --port 43594
```

Use `--skip-lobby` to connect directly to an older server that does not support lobby authentication.

The lobby initializer's first argument selects quick world login (0) or the lobby (1). The client supplies 1 to the native initializer when the lobby is enabled, so the cache does not immediately send the player back into the world.
