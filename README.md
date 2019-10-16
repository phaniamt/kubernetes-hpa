# kubernetes-hpa
      apiVersion: autoscaling/v1
      kind: HorizontalPodAutoscaler
      metadata:
        name: nginx-hpa
        namespace: default 
      spec:
        scaleTargetRef:
          apiVersion: apps/v1
          kind: Deployment
          name: awesome_app
        minReplicas: 3
        maxReplicas: 5
        targetCPUUtilizationPercentage: 85



      apiVersion: autoscaling/v1
      kind: HorizontalPodAutoscaler
      metadata:
        name: nginx-hpa
        namespace: default
      spec:
        scaleTargetRef:
          apiVersion: apps/v1
          kind: Deployment
          name: nginx
        minReplicas: 2
        maxReplicas: 10
        metrics:
        - type: Resource
          resource:
            name: memory
            targetAverageUtilization: 60
