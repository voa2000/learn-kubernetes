## Creating a Secret Using kubectl create secret
Say that some pods need to access a database. The username and password that the pods should use is in the files ./username.txt and ./password.txt on your local machine.

# Create files needed for rest of example.
```bash
echo -n 'admin' > ./username.txt
```
```bash echo -n '1f2d1e2e67df' > ./password.txt
```
The kubectl create secret command packages these files into a Secret and creates the object on the Apiserver.

```bash
kubectl create secret generic db-user-pass --from-file=./username.txt --from-file=./password.txt
secret "db-user-pass" created
```
