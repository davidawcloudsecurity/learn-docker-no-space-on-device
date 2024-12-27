# learn-docker-no-space-on-device
How to use other directory to pull image if no space on device

### Move Docker's Storage Location
If resizing the partition is not possible or doesn't resolve the issue, you can move Docker's data directory to another disk or partition with more space.

### Stop Docker:

```bash
sudo systemctl stop docker
```
### Move the Docker Data Directory (default /var/lib/docker):

### Move the Docker data directory to a location with more space (e.g., /mnt/docker):

```bash
sudo mv /var/lib/docker /mnt/docker
```
### Create a Symlink to the New Location:
```bash
sudo ln -s /mnt/docker /var/lib/docker
```
### Restart Docker:
```bash
sudo systemctl start docker
````
This should allow Docker to use the new location for storage.
