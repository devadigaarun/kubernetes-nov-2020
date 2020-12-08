# Volumes Orchestration

1. External Volumes are FIRST MOUNTED inside NODE and then
   to the containers

2. k8s has lots of storage provisioners, some of them provides 
	"ReadWriteMany" access policy (Multiple nodes can MOUNT
	same volume in READ/WRITE mode)

3. Storage Provisioners provide "storageclass" which defines the type
   of external storage.

	$ kubectl get storageclass / sc

4. Storage Class Properties

    Reclaim Policy : 		DELETE, RECYCLE, RETAIN

			RETAIN: After you remove volume from kubernetes, DO NOT delete
				the actual data.

			RECYCLE: After you remove volume from kubernetes, Mark the 						storage for next use. When you create new volume, 
				then data would be removed from the old storage.

			DELETE: After you remove volume, data is also deleted!

## Kubernetes Recommend:
	
    HostPath: DELETE 	(To Save space on local node)
	
    Cloud   : RETAIN	(Cloud Storage is cheaper and scalable)
	
    OnPremise : RECYCLE	(Storage on-premise is limited and should be re-used)

## Creating and Managing Volumes

1.  Static Volume Provisioning

    i.   Create the physical/cloud storage
    ii.  Attach it to Kubernetes Volumes
    iii. Add volume to POD

2.  Dynamic Volume Provisioning

    i.   Create the 'Volume Claim'
    ii.  Add 'volume claim' to PODs
    iii. Then storage would be created