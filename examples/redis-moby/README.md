# How To's for Examples

## redis-moby

Use three snapshots in the SAM

Example SAM

```
docker_app: docker-compose-app1.yml

flocker_hub:
    endpoint: http://<ip|dnsname>:<port>
    tokenfile: /root/vhut.txt

volumes:
    - name: redis-data
      snapshot: snapshotOf_first_volume
      volumeset: docker-app-example
    - name: artifacts
      snapshot: snapshotOf_first_volume_2
      volumeset: docker-app-example
    - name: /my/path
      snapshot: snapshotOf_first_volume_3
      volumeset: docker-app-example
```