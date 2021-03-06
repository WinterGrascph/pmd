---
title: Basic VF
summary: Rules concerning basic VF guidelines.
permalink: pmd_rules_vf_security.html
folder: pmd/rules/vf
sidebaractiveurl: /pmd_rules_vf.html
editmepath: ../pmd-visualforce/src/main/resources/rulesets/vf/security.xml
keywords: Basic VF, VfUnescapeEl, VfCsrf
---
## VfCsrf

**Since:** PMD 5.6.0

**Priority:** Medium (3)

Avoid calling VF action upon page load as the action becomes vulnerable to CSRF.

**This rule is defined by the following Java class:** [net.sourceforge.pmd.lang.vf.rule.security.VfCsrfRule](https://github.com/pmd/pmd/blob/master/pmd-visualforce/src/main/java/net/sourceforge/pmd/lang/vf/rule/security/VfCsrfRule.java)

**Example(s):**

``` vf
<apex:page controller="AcRestActionsController" action="{!csrfInitMethod}" >
```

## VfUnescapeEl

**Since:** PMD 5.6.0

**Priority:** Medium (3)

Avoid unescaped user controlled content in EL as it results in XSS.

**This rule is defined by the following Java class:** [net.sourceforge.pmd.lang.vf.rule.security.VfUnescapeElRule](https://github.com/pmd/pmd/blob/master/pmd-visualforce/src/main/java/net/sourceforge/pmd/lang/vf/rule/security/VfUnescapeElRule.java)

**Example(s):**

``` vf
<apex:outputText value="Potential XSS is {! here }" escape="false" />
```

