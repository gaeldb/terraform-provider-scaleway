## 1.13.1 (Unreleased)
## 1.13.0 (December 10, 2019)

BREAKING CHANGES:

* `scaleway_instance_placement_group`: change default policy from `low_latency` to `max_availability` ([#329](https://github.com/terraform-providers/terraform-provider-scaleway/pull/329)).
This change was made to keep coherence with default API behavior.
* `scaleway_instance_server`: The attribute `disable_dynamic_ip` has been removed in favor of `enable_dynamic_ip` ([#365](https://github.com/terraform-providers/terraform-provider-scaleway/pull/365)).
* `scaleway_instance_ip`: In order to resolve circular dependencies that can happen in some use case we changed
the way an IP is attached to a server. The attribute `scaleway_instance_ip.server_id` has been removed in
favor of `scaleway_instance_server.ip_id` ([#365](https://github.com/terraform-providers/terraform-provider-scaleway/pull/365)).

FEATURE:

* **New Data source**: `scaleway_baremetal_offer_beta` ([#361](https://github.com/terraform-providers/terraform-provider-scaleway/pull/361))
* **New Data source**: `scaleway_instance_image` ([#359](https://github.com/terraform-providers/terraform-provider-scaleway/pull/359))
* **New Data source**: `scaleway_instance_security_group` ([#346](https://github.com/terraform-providers/terraform-provider-scaleway/pull/346))
* **New Data source**: `scaleway_instance_server` ([#350](https://github.com/terraform-providers/terraform-provider-scaleway/pull/350))
* **New Data source**: `scaleway_instance_volume` ([#356](https://github.com/terraform-providers/terraform-provider-scaleway/pull/356))
* **New Data source**: `scaleway_marketplace_image` ([#362](https://github.com/terraform-providers/terraform-provider-scaleway/pull/362))
* **New Resource**: `scaleway_rdb_instance_beta` ([#331](https://github.com/terraform-providers/terraform-provider-scaleway/pull/331))
* **New Resource**: `scaleway_instance_ip_reverse_dns` ([#315](https://github.com/terraform-providers/terraform-provider-scaleway/pull/315))
`scaleway_baremetal_server_beta`: add support for offer name ([#345](https://github.com/terraform-providers/terraform-provider-scaleway/pull/345))
`scaleway_lb_backend_beta`: add tcp/http/https health check support ([#318](https://github.com/terraform-providers/terraform-provider-scaleway/pull/318))
`scaleway_k8s_cluster_beta`: add in place updates cluster ingress and dashboard ([#316](https://github.com/terraform-providers/terraform-provider-scaleway/pull/316))

BUG FIXES:

* `scaleway_k8s_cluster_beta`: handle regional IDs properly ([#320](https://github.com/terraform-providers/terraform-provider-scaleway/pull/320))
* `scaleway_lb_backend_beta`: health_check_delay is now properly used ([#357](https://github.com/terraform-providers/terraform-provider-scaleway/pull/357))
* `scaleway_instance_security_group`: make port-range editable ([#358](https://github.com/terraform-providers/terraform-provider-scaleway/pull/358))
* `scaleway_instance_server`: read server image during import ([#337](https://github.com/terraform-providers/terraform-provider-scaleway/pull/337))
* `scaleway_instance_server`: ignore case on instance types ([#312](https://github.com/terraform-providers/terraform-provider-scaleway/pull/312))
* `scaleway_object_bucket`: fix bucket import ([#343](https://github.com/terraform-providers/terraform-provider-scaleway/pull/343))
* `scaleway_provider`: better bootstrap error handling ([#342](https://github.com/terraform-providers/terraform-provider-scaleway/pull/342))


## 1.12.0 (October 25, 2019)

FEATURES:

* **New Resource:** `scaleway_lb_frontend_beta` ([#305](https://github.com/terraform-providers/terraform-provider-scaleway/pull/305))
* **New Resource:** `scaleway_lb_backend_beta` ([#303](https://github.com/terraform-providers/terraform-provider-scaleway/pull/303))
* **New Resource:** `scaleway_lb_beta` ([#278](https://github.com/terraform-providers/terraform-provider-scaleway/pull/278))
* **New Resource:** `scaleway_k8s_cluster` ([#258](https://github.com/terraform-providers/terraform-provider-scaleway/pull/258))
* **New Resource:** `scaleway_k8s_pool` ([#258](https://github.com/terraform-providers/terraform-provider-scaleway/pull/258))
* **New Resource:** `scaleway_account_ssh_key` ([#262](https://github.com/terraform-providers/terraform-provider-scaleway/pull/262))
* `scaleway_instance_server`: add ipv6 info on server resource ([#301](https://github.com/terraform-providers/terraform-provider-scaleway/pull/301))
* `scaleway_instance_security_group`: add ANY protocol ([#297](https://github.com/terraform-providers/terraform-provider-scaleway/pull/297))
* `scaleway_instance_server`: add disable_dynamic_ip ([#293](https://github.com/terraform-providers/terraform-provider-scaleway/pull/293))
* `scaleway_k8s_cluster`: add missing placement group ID ([#268](https://github.com/terraform-providers/terraform-provider-scaleway/pull/268))
* `scaleway_k8s_cluster`: add autohealing to pools ([#266](https://github.com/terraform-providers/terraform-provider-scaleway/pull/266))

BUG FIXES:

* `scaleway_account_ssh_key`: trim ssh key before sending it to the API (#304) ([#242](https://github.com/terraform-providers/terraform-provider-scaleway/issues/304))
* `scaleway_ip`: handle 403 error as a 404 in read function ([#300](https://github.com/terraform-providers/terraform-provider-scaleway/pull/300))
* `scaleway_baremetal_server_beta`: read OS.ID in os_id attribute ([#288](https://github.com/terraform-providers/terraform-provider-scaleway/pull/288))
* `scaleway_baremetal_server_beta`: remplace project_id by organization_id in read ([#277](https://github.com/terraform-providers/terraform-provider-scaleway/pull/277))
* `scaleway_k8s_cluster_beta`: do not update autoscaled pool size ([#265](https://github.com/terraform-providers/terraform-provider-scaleway/pull/265))


## 1.11.0 (October 01, 2019)

NOTES:

* Full documentation about this update, including Terraform provider version pinning and configuration examples, can be found in the [migration guide](https://www.terraform.io/docs/providers/scaleway/guides/migration_guide_v2.html).

FEATURES:

* provider/scaleway: new provider configuration ([#140](https://github.com/terraform-providers/terraform-provider-scaleway/issues/140))
* **New Resource:**: `scaleway_instance_server` ([#143](https://github.com/terraform-providers/terraform-provider-scaleway/issues/143))
* **New Resource:**: `scaleway_instance_ip` ([#143](https://github.com/terraform-providers/terraform-provider-scaleway/issues/143))
* **New Resource:**: `scaleway_instance_security_group` ([#143](https://github.com/terraform-providers/terraform-provider-scaleway/issues/143))
* **New Resource:**: `scaleway_instance_volume` ([#143](https://github.com/terraform-providers/terraform-provider-scaleway/issues/143))
* **New Resource:**: `scaleway_object_bucket` ([#143](https://github.com/terraform-providers/terraform-provider-scaleway/issues/143))
* **New Resource:**: `scaleway_account_ssh_key` ([#143](https://github.com/terraform-providers/terraform-provider-scaleway/issues/143))
* **New Resource:**: `scaleway_baremetal_server_beta` (in beta version) ([#143](https://github.com/terraform-providers/terraform-provider-scaleway/issues/143))

* **Deprecated Resource:**: `scaleway_server` (replaced by `scaleway_instance_server`) ([#143](https://github.com/terraform-providers/terraform-provider-scaleway/issues/143))
* **Deprecated Resource:**: `scaleway_ip` (replaced by `scaleway_instance_ip`) ([#143](https://github.com/terraform-providers/terraform-provider-scaleway/issues/143))
* **Deprecated Resource:**: `scaleway_ip_reverse_dns` (included into `scaleway_instance_ip`) ([#143](https://github.com/terraform-providers/terraform-provider-scaleway/issues/143))
* **Deprecated Resource:**: `scaleway_security_group` (replaced by `scaleway_instance_security_group`) ([#143](https://github.com/terraform-providers/terraform-provider-scaleway/issues/143))
* **Deprecated Resource:**: `scaleway_security_group_rule` (included into `scaleway_instance_security_group`) ([#143](https://github.com/terraform-providers/terraform-provider-scaleway/issues/143))
* **Deprecated Resource:**: `scaleway_volume` (replaced by `scaleway_instance_volume`) ([#143](https://github.com/terraform-providers/terraform-provider-scaleway/issues/143))
* **Deprecated Resource:**: `scaleway_volume_attachment` (included into `scaleway_instance_volume`) ([#143](https://github.com/terraform-providers/terraform-provider-scaleway/issues/143))
* **Deprecated Resource:**: `scaleway_user_data` (included into `scaleway_instance_server`) ([#143](https://github.com/terraform-providers/terraform-provider-scaleway/issues/143))
* **Deprecated Resource:**: `scaleway_bucket` (replaced by `scaleway_object_bucket`) ([#143](https://github.com/terraform-providers/terraform-provider-scaleway/issues/143))
* **Deprecated Resource:**: `scaleway_token` ([#143](https://github.com/terraform-providers/terraform-provider-scaleway/issues/143))
* **Deprecated Resource:**: `scaleway_ssh_key` (replaced by `scaleway_account_ssh_key`) ([#143](https://github.com/terraform-providers/terraform-provider-scaleway/issues/143))

BUG FIXES:

* provider/scaleway: update terraform SDK to 0.12.8 ([#242](https://github.com/terraform-providers/terraform-provider-scaleway/issues/242))


## 1.10.0 (June 03, 2019)

FEATURES

* provider/scaleway: update terraform SDK to 0.12.0 ([#127](https://github.com/terraform-providers/terraform-provider-scaleway/issues/127))

BUG FIXES:

* provider/scaleway: build command in the README ([#134](https://github.com/terraform-providers/terraform-provider-scaleway/issues/134))


## 1.9.2 (March 27, 2019)

BUG FIXES:

* datasource/image: sort results descending ([#117](https://github.com/terraform-providers/terraform-provider-scaleway/issues/117))
* provider/scaleway: load correct credentials from ENV ([#114](https://github.com/terraform-providers/terraform-provider-scaleway/pull/114))


## 1.9.1 (March 15, 2019)

BUG FIXES:

* provider/scaleway: load correct value from ENV ([#113](https://github.com/terraform-providers/terraform-provider-scaleway/pull/113))

## 1.9.0 (March 15, 2019)

FEATURES:

* provider/scaleway: the provider now tries to parse the Scaleway CLI configuration if no environment variables are set ([#111](https://github.com/terraform-providers/terraform-provider-scaleway/pull/111))

BUG FIXES:

* resource/scaleway_ssh_key: trim leading and trailing spaces on SSH keys ([#110](https://github.com/terraform-providers/terraform-provider-scaleway/pull/110))


## 1.8.0 (November 27, 2018)

FEATURES:

* **New Resource:**: `scaleway_ip_reverse_dns` ([#96](https://github.com/terraform-providers/terraform-provider-scaleway/pull/96))
* resource/scaleway_server: support cloudinit ([#97](https://github.com/terraform-providers/terraform-provider-scaleway/pull/97))
* resource/scaleway_security_group: support stateful security groups as well as default inbound and outbount policies ([#97](https://github.com/terraform-providers/terraform-provider-scaleway/pull/97))

## 1.7.0 (October 05, 2018)

FEATURES:

* **New Resource:** `scaleway_bucket` ([#94](https://github.com/terraform-providers/terraform-provider-scaleway/issues/94))

## 1.6.0 (August 28, 2018)

FEATURES:

* **New Data Source:** `scaleway_security_group` ([#78](https://github.com/terraform-providers/terraform-provider-scaleway/issues/78))
* **New Data Source:** `scaleway_volume` ([#77](https://github.com/terraform-providers/terraform-provider-scaleway/issues/77))
* resource/scaleway_image: support filtering by most recently created image ([#82](https://github.com/terraform-providers/terraform-provider-scaleway/pull/82))

BUG FIXES:

* resource/scaleway_token: fix compatability to changes in Scaleway API ([#86](https://github.com/terraform-providers/terraform-provider-scaleway/pull/86))
* resource/server: fix issue identifying restarts properly ([#87](https://github.com/terraform-providers/terraform-provider-scaleway/pull/87))

## 1.5.1 (July 11, 2018)

IMPROVEMENTS:

* provider: update documentation ([#75](https://github.com/terraform-providers/terraform-provider-scaleway/pull/75))

BUG FIXES:

* resource/scaleway_server & resource/scaleway_volume_attachment: race condition between startup & shutdown of servers ([#74](https://github.com/terraform-providers/terraform-provider-scaleway/pull/74))

## 1.5.0 (June 29, 2018)

IMPROVEMENTS:

* provider: update documentation ([#68](https://github.com/terraform-providers/terraform-provider-scaleway/pull/68), [#70](https://github.com/terraform-providers/terraform-provider-scaleway/pull/70))
* resource/scaleway_server: validate instance type availability ([#69](https://github.com/terraform-providers/terraform-provider-scaleway/pull/69))
* provider: update scaleway sdk ([#71](https://github.com/terraform-providers/terraform-provider-scaleway/pull/71))
* provider: allow concurrent creation of server resources ([#72](https://github.com/terraform-providers/terraform-provider-scaleway/pull/72))

## 1.4.1 (May 18, 2018)

BUG FIXES:

* resource/scaleway_server: fix server type validation ([#63](https://github.com/terraform-providers/terraform-provider-scaleway/pull/63))

## 1.4.0 (May 07, 2018)

IMPROVEMENTS:

* resource/scaleway_server: Update public_ip documentation ([#58](https://github.com/terraform-providers/terraform-provider-scaleway/pull/58))
* resource/scaleway_server: Add boot_type ([#59](https://github.com/terraform-providers/terraform-provider-scaleway/pull/59))

## 1.3.0 (April 11, 2018)

FEATURES:

* **New Resource:** `scaleway_token` ([#56](https://github.com/terraform-providers/terraform-provider-scaleway/pull/56))
* **New Resource:** `scaleway_user_data` ([#57](https://github.com/terraform-providers/terraform-provider-scaleway/pull/57))

IMPROVEMENTS:

* provider: update documentation ([#51](https://github.com/terraform-providers/terraform-provider-scaleway/pull/51),[#52](https://github.com/terraform-providers/terraform-provider-scaleway/pull/52))
* provider: update scaleway sdk ([#53](https://github.com/terraform-providers/terraform-provider-scaleway/pull/53), [#54](https://github.com/terraform-providers/terraform-provider-scaleway/pull/54), [#55](https://github.com/terraform-providers/terraform-provider-scaleway/pull/55))

BUG FIXES:

* provider: fix crash when working over slow and unreliable network connection ([#49](https://github.com/terraform-providers/terraform-provider-scaleway/pull/49))

## 1.2.0 (March 15, 2018)

IMPROVEMENTS:

* resource/scaleway_ip: Add support for setting reverse DNS field ([#48](https://github.com/terraform-providers/terraform-provider-scaleway/pull/48))
* resource/scaleway_ssh_key: Add new resource to manage ssh keys ([#47](https://github.com/terraform-providers/terraform-provider-scaleway/pull/47))

## 1.1.0 (February 27, 2018)

BUG FIXES:

* resource/scaleway_server: Fix crash with stopped server and ipv6 enabled ([#44](https://github.com/terraform-providers/terraform-provider-scaleway/issues/44))

IMPROVEMENTS:

* resource/scaleway_security_group: Add `enable_default_security` attribute to manage Scaleway default security group rules ([#43](https://github.com/terraform-providers/terraform-provider-scaleway/issues/43))

## 1.0.1 (January 15, 2018)

BUG FIXES:

* resource/scaleway_security_group_rule: Fix error when using count ([#25](https://github.com/terraform-providers/terraform-provider-scaleway/issues/25))
* provider: Retry rate-limited API requests ([#35](https://github.com/terraform-providers/terraform-provider-scaleway/issues/35))

IMPROVEMENTS:

* resource/scaleway_server: Validate types against scaleway offerings ([#17](https://github.com/terraform-providers/terraform-provider-scaleway/issues/17))

## 1.0.0 (October 25, 2017)

BUG FIXES:

* data-source/scaleway_bootscript: Fix crash when no filter is specified ([#21](https://github.com/terraform-providers/terraform-provider-scaleway/issues/21))

IMPROVEMENTS:

* resource/scaleway_server: Allow initial volumes without size to improve module support ([#19](https://github.com/terraform-providers/terraform-provider-scaleway/issues/19))

## 0.1.1 (August 04, 2017)

BUG FIXES:

* resource/scaleway_volume_attachment: Fix volume_attachment deletion ([#13](https://github.com/terraform-providers/terraform-provider-scaleway/issues/13))

IMPROVEMENTS:

* resource/scaleway_server: Improve public_ip attachment ([#14](https://github.com/terraform-providers/terraform-provider-scaleway/issues/14))

## 0.1.0 (June 21, 2017)

NOTES:

* Same functionality as that of Terraform 0.9.8. Repacked as part of [Provider Splitout](https://www.hashicorp.com/blog/upcoming-provider-changes-in-terraform-0-10/)
