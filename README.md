To use this test setup, you will need:

- [Kathara]
- [kathara-makelab]

[Kathara]: https://www.kathara.org/
[kathara-makelab]: https://github.com/larsks/kathara-makelab

To bring up a test scenario, first generate the kathara configurations:

```
make
```

Then `cd` into a scenario directory and bring up the environment:

```
$ cd scenario1-legacy-route
$ kathara lstart
```

To connect to a host defined in the configuration (`topology.yaml`):

```
$ katahara connect node0
root@node0:/#
```

To clean up when you're done:

```
$ kathara lclean
```

In both scenarios, `node0` is the node with the [ECMP] routing configuration and has interfaces on multiple `10.8.*.0/18` networks. Nodes `node1`, `node2`, and `node3` are on the `10.7.0.0/20` network. A router, `router0`, has interfaces on all of the above networks.

[ecmp]: https://en.wikipedia.org/wiki/Equal-cost_multi-path_routing
