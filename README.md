Ungrades with helm, while passing the `image.tag` value.

Example Usage

```yml
jobs:
  deploy:
    uses: sanguinelab/eks-deploy-with-helm/.github/workflows/eks-deploy-with-helm.yml@develop
    with:
      eks-cluster: my-cluster
      helm-release: my-release
      chart-directory: ./devops/helm
      values-file: ./devops/helm/values/values.staging.yaml
      image-tag: ${{ needs.build-and-push.outputs.image-tag }}
      eks-region: eu-central-1
    secrets:
      aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
      aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
```
