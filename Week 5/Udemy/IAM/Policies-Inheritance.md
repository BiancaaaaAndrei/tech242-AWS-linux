# IAM Policies Inheritance

#### Let's imagine we have a group of developers and attach a policy at the group level. In that case, the policy will get applied to every single member of the group so all will get access and inherit this policy:

![Alt text](<../../../readme-images/iam/poli inh.png>)

#### If having a second group with operations with a different policy, David and Edward will have a different policy than the group of developers:

![Alt text](<../../../readme-images/iam/poli inheri.png>)

#### If Fred is a user, it has the possibility not to belong to a group. And we have the possibility to create what's called an INLINE POLICY which has a policy that's only attached to a user:

![Alt text](<../../../readme-images/iam/poli inherit.png>)

#### If Charles and David both belong to the audit team and you attach a policy to the audit team as well, Charles and David will also inherit that policy from the audit team:

![Alt text](<../../../readme-images/iam/poli inheritance.png>)

- So in this case, Charles has a policy from developers and a policy from audit team.

- And David has a policy from audit team and a policy from the operations team.


## Policy structure

- Consists of a **version number**, so usually it's 2012-10-17, this is the policy language version.

- **ID** which is how to identify that policy, this is optional.

- **More statements**, and statements can be one or multiple ones, and a statement has some very important parts:
  - **Sid** is a statement ID, which is an identifier for the statement, which is optional as well.
  - **Effect** of the policy itself, so it is whether or not the statement allows or denies access to certain API.
  - **Principal** consists of which accounts, user or role which, to which this policy will be applied to. So in this example, it's applied to the root accounts of your AWS accounts.
  - **Action** is the list of API calls that will be either denied or allowed based on the effect.
  - **Resource** is a list of resources, to which the actions will be applied to.

![Alt text](<../../../readme-images/iam/poli structure.png>)
