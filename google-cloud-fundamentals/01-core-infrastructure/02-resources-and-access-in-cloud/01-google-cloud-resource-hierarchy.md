Google cloud resource hierarchy contains four levels (from bottom up):
- Resources
	- represent virtual machines, cloud storage buckets, tables in BigQuery or anything in Google Cloud
- Projects
	- Resources can be organized into projects
- Folders
	- Projects can be organized into folders, or even subfolders.
- Organization
	- Top level, which encompasses all the projects, folders, and resources in your organization

![[cloud-hierarchy.svg|400]]

The resource hierarchy directly relates to how policies are managed and applied on Google Cloud
- Policies can be defined at the project, folder, and organization node levels
- Policies are inherited downward means that if you apply policy to a folder, it will also apply to all of the projects within that folder

Project Resource Hierarchy
- Basis for enabling and using GCP services, like managing APIs, enabling billing, adding and removing collaborators, and enabling other services
	- projects are separate entities under the Organization node
	- projects hold resources, each of which belongs to just one project
	- projects can have different owners and users
	- projects are billed and managed separately
- Each GCP Project has three identifying attributes: 
	- Project ID
		- A globally unique identifier assigned by GCP that can't be changed after creation
		- Immutable after creation
		- Used in different contexts to inform Google Cloud of the exact project to work with
	- Project name
		- user-created and don't have to be unique
		- Mutable
	- Project number
		- Globally unique and assigned by GCP
		- Immutable
		- Used internally by GCP to keep track of resources

Google Resource Manager Tool
- An API that can 
	- Gather a list of projects
	- Create new projects
	- Update existing projects
	- Delete projects.
	- Recover previously deleted projects
	- Access through the RPC API and the REST API

Folder Resource Hierarchy
- Folder let you assign policies to resources at a level of granularity you choose
- The resources in a folder inherit policies and permissions assigned to that folder
- A folder can contain projects, other folders, or a combination of both
- Use folders to group projects under an organization in a hierarchy
- For example, your organization might contain multiple departments, each with its own set Google Cloud resources
- Folders allow you to group these resources on a per-department basis
- Folders also give teams the ability to delegate administrative rights so that they can work independently

Organization Resource Hierarchy
- There are some special roles associated with this top-level organization node
- For example, you can designate an organization policy administrator so that only people with privilege can change policies
- You can also assign a project creator role, which is a great way to control who can create projects and, therefore, who can spend money
