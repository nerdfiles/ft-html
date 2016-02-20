# FT-HTML

A Reference Architecture for field modeling markup of discovered resources 
at the application layer within the TCP/IP stack concerning various layouts 
of [Broadly Layered Distributed Systems][0]. Ideally a system like Bitcoin 
could be described as a Broadly Layered system such that subsystem layers 
can be richly declared in HTML. 

So, consider a fictional outline of a (potentially) Broadly Layered system 
of Bitcoin:

1. Network Layer  
   Capabilities might involve `recovery` or `reconfig`
2. Serialization Layer  
   Capabilities might involve `sequential-retry` or `reconfig`
3. P2P Layer  
   Capabilities might involve `parallel-recovery` or `reintegration`
4. Memory Pool Layer  
   Capabilities might involve `parallel-diagnosis` or `rollback`
5. Chaining Layer  
   Capabilities might involve `restart` or `repair`
6. Sanitization Layer  
   Capabilities might involve `reintegrate` or `rollback`
7. Wallet Layer  
   Capabilities might involve `retry` or `skip` or `mask`

## Overview

FT-HTML presupposes a layered system substrate to underpin Structural Meaning 
as [link relations][1]. We are injecting a dictionary of fault-tolerance link 
relation types, largely informed by Principles of URI/ID Design. 

<p align="center">
<img src="H Factors - HTML" src="http://amundsen.com/images/hypermedia/hfactors-html.png" />
</p>

FT-relations as *control links* share the namespace of link relations, typically 
descriptive of internetworking documents. FT-relations are Structural Meanings, 
as opposed to Semantic Meanings which describe Accessibility, whose purpose is 
to declaratively implement the Availability of the any general-purpose 
distributed network and annotate control data with fault-tolerance strategies as 
FT Factors, or FT Extensions, or FT Support for distributed Asset-centric [Media Types](http://amundsen.com/hypermedia/hfactor/).

We outline Reference Implementation Examples to elucidate where value is met in 
such an extension to HTML. The following may be prefixed with `ft-*`:

    Diagnosis
    Reconfig (See Tendermint, but with bettyfiles as the config space)
    Recovery
    Restart
    Repair
    Reintegration
    Retry
    Rollback
    Mask
    Skip
    Confinement
    Sequential
    Parallel
    Composite (combinations of Sequential and/or Parallel)

Think of the above list as Operational Strategies which assume Discoverability 
of the relevant REST-based microservice, assuming that it is REST-ful. 
WebSockets or HTTP/2 should have no bearing on the progressively-enhanced 
markup. At the end of the day, endpoints will server JSONAPI payloads with 
link relations for discoverability.

If we consider a [MOVE](https://cirw.in/blog/time-to-move-on) Application Pattern, 
we can more readily imagine the synthesis of Hypermedia View-based Modeling 
as our macro-field modeling strategy such that Fault-tolerance is expressed 
through combinatorics around Operational Strategies which address fault 
conditions, etc.

## Simple Example

    <a 
      role=”button”
      rel=”payment sequential-retry” 
      href=”{{paymentUri}}”
    >
      <link 
        rel=”reconfig” 
        href=”{{paymentConfigUri}}” 
      />
      {{hypertextContent}}
    </a>

[0]: https://www.eecs.umich.edu/techreports/cse/94/CSE-TR-201-94.pdf
[1]: http://www.iana.org/assignments/link-relations/link-relations.xhtml
