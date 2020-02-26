NAMESPACE: default
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
You have successfully installed IPFS in your kubernetes cluster!

You can access the IPFS API from inside your cluster by connecting to port 5001 on
    ipfs-ipfs.default

You can also connect to port 8080 on the same hostname for talking to the IPFS Gateway.


If you want to connect to it from your local computer, you can find a URL to connect with the
following (for the gateway service):
  export POD_NAME=$(kubectl get pods --namespace default -l "app=ipfs,release=ipfs"  -o jsonpath="{.items[0].metadata.name}")
  echo "Use the API Gateway by accessing http://localhost:8080/ipfs/<IPFS-HASH>"
  kubectl --namespace default port-forward $POD_NAME 8080:8080


kubectl --namespace default port-forward $POD_NAME 8080:8080 5001:5001 &