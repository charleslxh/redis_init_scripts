# redis_init_scripts
redis boot script, include start, stop, restart command line

1. Download script.
2. Copy the init script that you'll find in the Redis distribution under the utils directory into `/etc/init.d`. We suggest calling it with the name of the port where you are running this instance of Redis. For example:
    ```bash
    sudo cp redis_init_script /etc/init.d/redis
    ```

3. Copy `redis_6379` script to `/usr/local/bin/`:
    ```bash
    sudo cp redis_init_script /usr/local/bin/redis
    ```

4. Add the new Redis init script to all the default runlevels using the following command:
    ```bash
    sudo update-rc.d redis defaults
    ```

5. Restart terminel. You are done! Now you can try running your instance with:
    ```
    # start, default port is 6379.
    sudo redis start

    # restart
    sudo redis restart -p 6379 -f

    # stop
    sudo redis stop -p 6379
    ```
