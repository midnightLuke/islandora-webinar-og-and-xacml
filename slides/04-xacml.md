# XACML


## What is it?

Stands for "e**X**tensible **A**ccess **C**ontrol **M**arkup **L**anguage"

According to wikipedia:

> The standard defines a declarative fine-grained, attribute-based access control policy language, an architecture, and a processing model describing how to evaluate access requests according to the rules defined in policies.


## How does Islandora use it

- [Islandora XACML Editor](https://github.com/Islandora/islandora_xacml_editor) module
  - Provides a graphical editor as well as an API for developers
- Stores XACML policies in the **POLICY** datastream
- Allows "role" and "user" security identities
  - Uses the drupal filter to send to fedora for authentication

Notes:

- "Security identity" is something that you can grant/restrict access to


## What does a POLICY datastream look like?

```xml
<Policy PolicyId="islandora-xacml-editor-v1" RuleCombiningAlgId="urn:oasis:names:tc:xacml:1.0:rule-combining-algorithm:first-applicable" xmlns="urn:oasis:names:tc:xacml:1.0:policy" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <Target>
    <Subjects>
      <AnySubject/>
    </Subjects>
    <Resources>
      <AnyResource/>
    </Resources>
    <Actions>
      <AnyAction/>
    </Actions>
  </Target>
  <Rule Effect="Deny" RuleId="deny-management-functions">
    <Target>
      <Subjects>
        <AnySubject/>
      </Subjects>
      <Resources>
        <AnyResource/>
      </Resources>
      <Actions>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-addDatastream
</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-addDisseminator
</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-adminPing</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-getDisseminatorHistory
</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-getNextPid</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-ingest</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-modifyDatastreamByReference
</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-modifyDatastreamByValue
</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-modifyDisseminator
</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-modifyObject</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-purgeObject</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-purgeDatastream
</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-purgeDisseminator
</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-setDatastreamState
</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-setDisseminatorState
</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-setDatastreamVersionable
</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-compareDatastreamChecksum
</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-serverShutdown
</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-serverStatus</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-upload</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-dsstate</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-resolveDatastream
</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-reloadPolicies
</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
      </Actions>
    </Target>
    <Condition FunctionId="urn:oasis:names:tc:xacml:1.0:function:not">
      <Apply FunctionId="urn:oasis:names:tc:xacml:1.0:function:or">
        <Apply FunctionId="urn:oasis:names:tc:xacml:1.0:function:string-at-least-one-member-of">
          <SubjectAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:subject:loginId" DataType="http://www.w3.org/2001/XMLSchema#string" MustBePresent="false"/>
          <Apply FunctionId="urn:oasis:names:tc:xacml:1.0:function:string-bag">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">adminUP</AttributeValue>
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">fedoraAdmin</AttributeValue>
          </Apply>
        </Apply>
        <Apply FunctionId="urn:oasis:names:tc:xacml:1.0:function:string-at-least-one-member-of">
          <SubjectAttributeDesignator AttributeId="fedoraRole" DataType="http://www.w3.org/2001/XMLSchema#string" MustBePresent="false"/>
          <Apply FunctionId="urn:oasis:names:tc:xacml:1.0:function:string-bag">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">administrator</AttributeValue>
          </Apply>
        </Apply>
      </Apply>
    </Condition>
  </Rule>
  <Rule Effect="Deny" RuleId="deny-access-functions">
    <Target>
      <Subjects>
        <AnySubject/>
      </Subjects>
      <Resources>
        <AnyResource/>
      </Resources>
      <Actions>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:api-a</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:api" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-getDatastreamHistory
</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
        <Action>
          <ActionMatch MatchId="urn:oasis:names:tc:xacml:1.0:function:string-equal">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">urn:fedora:names:fedora:2.1:action:id-listObjectInResourceIndexResults
</AttributeValue>
            <ActionAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:action:id" DataType="http://www.w3.org/2001/XMLSchema#string"/>
          </ActionMatch>
        </Action>
      </Actions>
    </Target>
    <Condition FunctionId="urn:oasis:names:tc:xacml:1.0:function:not">
      <Apply FunctionId="urn:oasis:names:tc:xacml:1.0:function:or">
        <Apply FunctionId="urn:oasis:names:tc:xacml:1.0:function:string-at-least-one-member-of">
          <SubjectAttributeDesignator AttributeId="urn:fedora:names:fedora:2.1:subject:loginId" DataType="http://www.w3.org/2001/XMLSchema#string" MustBePresent="false"/>
          <Apply FunctionId="urn:oasis:names:tc:xacml:1.0:function:string-bag">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">adminUP</AttributeValue>
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">fedoraAdmin</AttributeValue>
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">ilovan</AttributeValue>
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">brundin</AttributeValue>
          </Apply>
        </Apply>
        <Apply FunctionId="urn:oasis:names:tc:xacml:1.0:function:string-at-least-one-member-of">
          <SubjectAttributeDesignator AttributeId="fedoraRole" DataType="http://www.w3.org/2001/XMLSchema#string" MustBePresent="false"/>
          <Apply FunctionId="urn:oasis:names:tc:xacml:1.0:function:string-bag">
            <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">administrator</AttributeValue>
          </Apply>
        </Apply>
      </Apply>
    </Condition>
  </Rule>
  <Rule Effect="Permit" RuleId="allow-everything-else">
    <Target>
      <Subjects>
        <AnySubject/>
      </Subjects>
      <Resources>
        <AnyResource/>
      </Resources>
      <Actions>
        <AnyAction/>
      </Actions>
    </Target>
  </Rule>
</Policy>
```


## Pros/Cons

- **PRO**: Works with fedora
- **PRO**: Policies are stored in repository
- **CON**: Hard to use
- **CON**: Not very extensible
