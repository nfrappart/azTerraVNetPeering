# Required Resources
- existing resource group
- existing VNet

# Example Usage

```hcl
module "peering-spoke2-to-hub" {
  source                         = "github.com/nfrappart/azTerraVNetPeering?ref=v1.0.1"
  VNetPeeringName                = "peering-test"
  RgName                         = module.rg-core-eu.Name
  LocalVNetName                  = module.vn-spoke2-eu.Name
  RemoteVNetId                   = module.vn-hub-eu.Id
  IsVirtualNetworkAccessAllowed = "false"
  IsForwardedTrafficAllowed      = "false"
  IsGWTransitAllowed             = "false"
  UseRemoteGW                    = "false"
}
```
