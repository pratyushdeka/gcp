When an organization node contains lots of folders, projects, and resources, a workforce might need to restrict who has access to what. To help with this task, administrators can use Identity and Access Management, or IAM.

With IAM, administrators can apply policies that define who can do what and on which resources.

Principal
- who part of an IAM policy
- Can be a 
	- Google account
	- Google group
	- Service account
	- Cloud identity domain
- Each principal has its own identifier, usually an email address

Role
- "can do what" part of an IAM policy
- A IAM role is a collection of permissions
- When you grant a role to a principal, you grant all the permissions that the role contains and also inherited through the resource hierarchy
	- For example, to manage virtual machine instances in a project, you must be able to create, delete, start, stop and change virtual machines
- Can define deny rules that prevent certain principals from using certain permissions, regardless of the roles they're granted
- IAM always checks relevant deny policies before checking relevant allow policies
- Deny policies, like allow policies, are inherited through the resource hierarchy
- Three kinds of IAM roles
	- Basic
		- Broad in scope
		- Includes
			- Owner - view, edit, manage associated roles & permissions, setup billing
			- Editor - view, edit
			- Viewer - view
			- Billing Admin - view, setup billing
		- A word of caution: If several people are working together on a project that contains sensitive data, basic roles are probably too broad.
	- Predefined
		- Specific Google Cloud services offer sets of predefined roles, and they even define where those roles can be applied
		- With Compute Engine, you can apply specific predefined roles—such as “instanceAdmin”—to Compute Engine resources in a given project, a given folder, or an entire organization
	- Custom
		- Many companies use a “least-privilege” model in which each person in the organization is given the minimal amount of privilege needed to do their job
			- For example, you want to define an “instanceOperator” role to allow some users to stop and start Compute Engine virtual machines, but not reconfigure them
		- Custom roles will allow to define those exact permissions
		- Two important consideration
			- You’ll need to manage the permissions that define the custom role you’ve created
			- Custom roles can only be applied to either the project level or organization level. Can't be applied to folder level
