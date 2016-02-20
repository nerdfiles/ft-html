# FT-HTML

A Reference Architecture for field modeling markup at the application layer 
within the TCP/IP concerning various layouts of Broadly Layered Distributed 
Systems.

## Overview

FT-HTML presupposes a layered system substrate to underpin Structural Meaning 
as *link relations*. We are injecting a dictionary of fault-tolerance link 
relation types, largely informed by Principles of URI/ID Design. 

Said article informs a broader space of Structural Meaning, whereas our 
purpose here is to offer up the prototypal default namespace of 
fault-tolerance, and, with any luck, Reference Implementation Examples to 
elucidate where value is met in such an extension to HTML. The following may 
be prefixed with `FT-*`:

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
