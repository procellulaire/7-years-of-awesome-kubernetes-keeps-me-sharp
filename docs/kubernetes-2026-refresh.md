# Kubernetes 2026 Study and Operations Refresh

This page is a dated starting point for Kubernetes study, research, and production
work. It complements the older, topic-specific links in this repository; always
check the upstream documentation for the Kubernetes version that you operate.

## Start with the upstream sources

- [Kubernetes documentation](https://kubernetes.io/docs/) — concepts, tasks,
  references, and tutorials.
- [Kubernetes releases](https://kubernetes.io/releases/) — supported release
  lines, release notes, and end-of-life information.
- [Kubernetes release blog](https://kubernetes.io/blog/) — feature graduations,
  deprecations, and project announcements.
- [Kubernetes enhancement proposals (KEPs)](https://github.com/kubernetes/enhancements/tree/master/keps)
  — the design history behind significant changes.
- [Kubernetes community calendar](https://calendar.kubernetes.io/) — release
  and community events.

## A practical 2026 learning path

1. **Fundamentals:** API objects, declarative reconciliation, scheduling,
   Services, DNS, storage, and workload controllers.
2. **Cluster operations:** bootstrap and upgrades, etcd backup and restore,
   [version skew policy](https://kubernetes.io/releases/version-skew-policy/),
   node lifecycle, resource requests and limits, and capacity planning.
3. **Networking:** CNI fundamentals, NetworkPolicy, Services, and the
   [Gateway API](https://gateway-api.sigs.k8s.io/); treat Ingress as a
   compatibility concern when planning new platforms.
4. **Security:** least-privilege RBAC, service accounts, Pod Security
   Standards, admission control, image provenance, secrets handling, and
   [Kubernetes security guidance](https://kubernetes.io/docs/concepts/security/).
5. **Reliability:** probes, disruption budgets, topology spread, graceful
   termination, autoscaling, observability, and tested disaster recovery.
6. **Platform engineering:** GitOps, policy as code, golden paths, multi-tenancy
   boundaries, cost visibility, and a documented ownership model.

## Topics worth revisiting in 2026

- [Gateway API](https://gateway-api.sigs.k8s.io/) for portable, expressive
  service networking.
- [Dynamic Resource Allocation](https://kubernetes.io/docs/concepts/scheduling-eviction/dynamic-resource-allocation/)
  for specialized hardware and device-aware scheduling.
- [Sidecar containers](https://kubernetes.io/docs/concepts/workloads/pods/sidecar-containers/)
  and ordered startup and shutdown for multi-container Pods.
- [In-place Pod vertical scaling](https://kubernetes.io/docs/tasks/configure-pod-container/resize-container-resources/)
  where supported by the cluster version and workload.
- [Validating admission policies](https://kubernetes.io/docs/reference/access-authn-authz/validating-admission-policy/)
  for CEL-based guardrails without a custom webhook for every rule.
- [Observability](https://kubernetes.io/docs/concepts/cluster-administration/cluster-management/)
  that correlates metrics, logs, traces, events, and control-plane health.

## Upgrade checklist

- Record the current Kubernetes, node, CNI, CSI, ingress or Gateway, and
  add-on versions.
- Read the release notes and deprecation guide for every version skipped.
- Run API compatibility and manifest checks before changing the control plane.
- Verify backup restore, admission policies, Pod Security settings, and workload
  disruption budgets in a representative environment.
- Upgrade one environment at a time, monitor control-plane and workload signals,
  and keep a tested rollback or recovery procedure.

> Version-specific behaviour wins over this summary. Pin links and examples to
> the version under test, and re-check this page when a new release line ships.
