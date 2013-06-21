payload
=======

Payload -- Cloud enabled content binding with dead simple setup.

Sometimes a developer is tasked with making an existing static site CMS-enabled.

Often times the client wants to be able to update very simple data such as bios, menus, events, images, etc.

These examples are mostly simple text, tablular data, or lists.

Without the luxury of having built the site from the ground up, the options are pretty bleak.

Usually you are faced with:

  1. Manually updating the site yourself, or trusting the client with the raw files.
  2. Migrating the site to a framework, like Wordpress, then train the client in the ways of the CMS editor.
  3. Writing an ad hoc solution.
  4. Using one of the minimal CMS frameworks out there.  This is a good option.

The goal of this project is:

  1. Allow the developer to easily create a custom CMS for the client that show *only* the exact fields to fill in.
  2. Require the utmost minimal additions to existing codebase.

Here is the basic flow:

  1. Customer requests that an area of the site needs to be periodically updated.
  2. The developer goes to payloadcms.com and creates an account.
  3. The developer creates a CMS instance (basically a project) for the target site.
  4. Using a form editor and other slick tools, they create a form for the client to fill in.
  5. The developer select a theme for the CMS and a username/password for the client.
  6. The system will generate an id for you for *each* field, like PayloadAboutUsTextarea.
  7. Now, in each .html, .php, etc page that the client wants editable the developer must put a script tag that is also provde by the Payload sytem.
  8. Then the developer must at each place that is to update put a div like <div data-payload-id='PayloadAboutUsTextarea'></div>.

That's it! So now when the clients page is hit, the Payload javascript file is loaded that corresponds to this customer's data.

The script will attempt to load the data first from local storage.

If it can't find it there, or it is expired, it will fetch the content from the payload servers.

When the script has the content, it will find the appropriate div and dynamically fill in the content.





