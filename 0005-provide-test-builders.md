# 5. Provide Test Builders

Date: 2018-06-06

## Status

Proposed

## Context

When creating tests, it helps to have good bean objects. But when you
need a bigger structure of some objects, it's a big thing to create them
on demand. It would be nice to have a builder pattern implemented for
most objects. This is of course depending on the language and the tools
used.

## Decision

For `java`, create a `Builder` for each object that creates default
values for tests but can have them easily be overwritten.  
Here's an example:

``` java
public class CustomerBuilder {

  private String companyName;
  private Address address;

  public CustomerBuilder() {
    this.companyName = "ACME Inc.";
    this.address = new AddressBuilder().build();
  }

  public CustomerBuilder withCompanyName(String companyName) {
    this.companyName = companyName;
    return this;
  }

  public CustomerBuilder withoutCompanyName() {
    this.companyName = null;
    return this;
  }

  public CustomerBuilder withAddress(Address address) {
    this.address = address;
    return this;
  }

  public CustomerBuilder withoutAddress() {
    this.address = null;
    return this;
  }

  public Company build() {
    Company result = new Company();
    result.setCompanyName(this.companyName);
    result.setAddress(this.address);
    return result;
  }
}
```

## Consequences

No consequences yet, as this is still a proposal. But as a consequence,
there shall always be a simple way to retrieve objects for the tests.
