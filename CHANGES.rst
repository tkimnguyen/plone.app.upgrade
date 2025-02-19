Changelog
=========

1.3.19 (unreleased)
-------------------

New:

- reapply profile for site-controlpanel
  plone/Products.CMFPlone#124
  [fgrcon]
  
- extended step to501 with reindexing getIcon (#1226)
  [fgrcon]

- Removed fake kupu tool and related settings and resources.
  [maurits]

- Cleanup the skins tool.
  [maurits]

- Cleanup uninstalled products.  Remove uninstalled products from QI
  and mark their installed profile version as unknown.
  [maurits]

- If non installable profiles (really: hidden profiles) have been
  installed in GS, mark their products as installed in the QI.  This
  does not work when also that *product* is marked as non installable,
  because in normal operation (outside of plone.app.upgrade) this does
  not happen either.
  [maurits]

- Unmark installed profiles that are no longer available.
  [maurits]

Fixes:

- Fixed removal of Large Plone Folder when migrating from Plone 3.
  [maurits]


1.3.18 (2015-09-27)
-------------------

- Add migration for ILinkSchema
  [vangheem]

- Add migration for TinyMCE settings
  [vangheem]

- Fix migration of typesUseViewActionInListings to registry.
  [pbauer]

- Fix incorrect interate import.
  [alecm]


1.3.17 (2015-09-22)
-------------------

- Fix issues with missing registry-entries when upgrading 5.0rc2 -> 5.0rc3.
  [pbauer]


1.3.16 (2015-09-20)
-------------------

- Plone 4.3: upgrade TinyMCE correctly.  Update sunburst theme profile
  version when applying its upgrade step.  Update CMFEditions.  Update
  plone.app.jquery.
  This fixes
  https://github.com/plone/Products.CMFPlone/issues/812
  [maurits]

- Portal properties calendar_starting_year and calendar_future_years_available
  were moved to registry.
  [pbauer]

- Remove unused invalid_ids portal property
  [esteele]


1.3.15 (2015-09-11)
-------------------

- Fix migration of types_not_searched to registry.
  Fixes https://github.com/plone/plone.app.contenttypes/issues/268
  [pbauer]

- Remove site properties that have been migrated to the registry.
  [esteele]


1.3.14 (2015-09-08)
-------------------

- Remove no-longer-used properties from portal_properties
  [esteele]

- Remove plone_forms skins folder for 5.0 rc1
  [esteele]

- Install plone.app.linkintegrity and migrate linkintegrity-relations.
  [pbauer]


1.3.13 (2015-08-23)
-------------------

- Unregister removed collection.css.
  [pbauer]

- 5.0 beta: do not set ``url_expr`` on configlet.  This must be done
  with ``setActionExpression``.
  Fixes https://github.com/plone/Products.CMFPlone/issues/814
  [maurits]

- Turn @@tinymce-controlpanel ``content_css`` field into a list
  [ebrehault]


1.3.12 (2015-07-23)
-------------------

- Fix for 5.0b2 -> 5.0b3 upgrade step that removed permissions from most of
  the control panel configlets. This fixes:
  https://github.com/plone/Products.CMFPlone/issues/745
  [sneridagh, timo]


1.3.11 (2015-07-20)
-------------------

- upgrade plone buttons to not have so many things open in modals
  [vangheem]

- uninstall mockup-pattern-accessibility pattern registration
  [vangheem]

- add Products.CMFPlacefulWorkflow as dep as __init__ requires this
  [maartenkling]

- add social media control panel upgrade
  [vangheem]

- upgrades for plone 5 tinymce configuration and social tags config
  [vangheem]

- add step for updated dropzone resource location
  [vangheem]

- remove plone.app.jquery dependency
  [vangheem]

- Add jquerytools removal upgrade
  [vangheem]

- Plone 5: upgrade manage portlets js
  [vangheem]

- Remove hard dependency on CMFDefault
  [tomgross]

- Update the category configlet of all the configlets in order to provide a way
  to categorize properly each configlet [sneridagh]

- Updated links for the renamed 'Types' control panel [sneridagh]


1.3.10 (2015-05-13)
-------------------

- Plone 4.3: Enable NewsML feed syndication
  [tcurvelo]

- Plone 5: Migrate imagine control panel settings to the configuration
  registry
  [vangheem]

- Plone 5: Solve CMFPlacefulWorkflow __iro__ problem because
  of moving their paths when upgrading
  [bloodbare]


1.3.9 (2015-03-26)
------------------

- LanguageTool/plone.app.multilingual migration
  [bloodbare]

- Update tests after removal of ``allowAnonymousViewAbout`` and
  ``validate_email`` properties in CMFPlone.
  [jcerjak]

- Do not run tests not suited for the current Plone version
  (implemented for 4.0 and below)
  [jensens]

- Add upgrade step for the security control panel.
  [jcerjak]

- Add upgrade step for mail control panel. Refs PLIP 10359.
  [jcerjak, khink]

- Add upgrade steps for markup control panel.
  [thet]


1.3.8 (2014-11-01)
------------------

- Add upgrade steps for editing, maintenance, navigation, search,
  and site control panels.
  [tisto]


1.3.7 (2014-10-22)
------------------

- Add upgrade-profile for vs5002 and update rolemap.xml to include
  "Mail forgotten password"-permission also to Managers.
  [ida]

- Added upgrade step for plone.app.querystring which adds new operations and
  fields
  [ichim-david]

- Plone 5 upgrade: Respect previous installed plone.app.event when migrating
  first_weekday setting.
  [thet]

- #12286 Need (Plone 4.0 upgrade) migration step for hidden static text
  portlets
  [anthonygerrard]

- provide upgrade step for plone.protect
  [vangheem]


1.3.6 (2014-03-02)
------------------

- Migrate theme settings, install Barceloneta.
  [davisagli]

- Migrate Members folder default view
  [davisagli]


1.3.5 (2014-02-19)
------------------

- Be sure the improved syndication settings introduced in the 4.3 series
  are applied on upgrade.
  [gbastien]

- Avoid failure at lexicon upgrade (4.3rc1)
  when we have an integrity error into the ZCTextIndex.
  [thomasdesvenain]

- Install plone.app.event and remove portal_calendar when upgarding to Plone 5.
  [davisagli]

- Remove portal_interface when upgrading to Plone 5.
  [ale-rt]

- Remove portal_actionicons, portal_discussion, and portal_undo when
  upgrading to Plone 5.
  [davisagli]

- Add condition to the upgrade step to add scaling-quality 4.3-final.
  plone.app.imaging no longer has the imaging_properties (moved to CMFPlone)
  so they are not there in plone5-tests.
  [pbauer]

- Add conditional install of plonetheme.classic in upgrade step 4.0a1. Since
  plonetheme.classic will be removed in Plone 5, we can not be sure that it
  is always installed.
  [timo]

- Replace deprecated test assert statements.
  [timo]

- Add undeclared Products.TinyMCE dependency.
  [timo]

- Add use_uuid_as_userid site property in Plone 5.
  Part of PLIP 13419.
  [maurits]

- Use lowercase for email login in Plone 5.
  Part of PLIP 13419.
  [maurits]

- Remove persistent kss_mimetype import step.
  [maurits]

- Fix name of Plone 5 zcml conditional feature to plone-5.
  [thet]

- Don't fail on out of date catalog when upgrading syndication for 4.3
  [tomgross]

- Add Default Plone Password Policy to Plone's acl_users.
  [gbastien]

1.3.4 (2013-08-14)
------------------

- Replace basic infrastructure for 4.4 series with same for 5.0 series.
  [davisagli]

- Upgrade TinyMCE: Remove space from style to prevent bogus class.
  [maurits]


1.3.3 (2013-06-13)
------------------

- Add upgrade step to set image scaling quality (p.a.imaging 1.0.8).
  [khink]

- Upgrade broken 'added' content rules.
  [thomasdesvenain]

- handle syndication upgrade when folder is not syndication enabled but
  has syndication information.
  [vangheem]


1.3.2 (2013-05-30)
------------------

- Nothing changed yet.


1.3.1 (2013-04-13)
------------------

- Fix upgrade-step upgradeSyndication for Dexterity
  [pbauer]


1.3 (2013-04-06)
----------------

- Add basic upgrade infrastructure for the Plone 4.4 series.
  [davisagli]

- Do not import Products.kupu. Fixes https://dev.plone.org/ticket/13480
  [danjacka]


1.3rc1 (2013-03-05)
-------------------

- add step for rc1 to upgrade catalog correctly
  [vangheem]

- Avoid hard dependency on ATContentTypes.
  [davisagli]


1.3b2 (2013-01-17)
------------------

- Run plonetheme.sunburst 1.4 upgrade.
  [esteele]

- Add upgrade step for plone.app.discussion.
  [toutpt]


1.3b1 (2013-01-01)
------------------

- Make sure the syndication upgrade step unregisters the old tool
  as a utility.
  [davisagli]

- Add upgrade for version 4.3b1 to make sure TinyMCE is upgraded.
  [davisagli]

- In the UID index migration, if there are items whose key is None,
  skip them instead of complaining about there being multiple items.
  [davisagli]


1.3a2 (2012-10-18)
------------------

- Add upgrade step to remove KSS.
  [vangheem, davisagli]

- Remove old upgrades that depended on KSS being present.
  [davisagli]

- Make sure registry settings for syndication and ResourceRegisties bundles
  are set up for Plone 4.3.
  [vangheem, davisagli]

- Make plone.app.theming upgrade steps only run when plone.app.theming is
  installed (i.e. not for a plain Products.CMFPlone site.)
  [elro]

1.3a1 (2012-08-31)
------------------

- Added Plone 4.3 upgrade step to apply plone.app.jquery 1.5 upgrade step.
  [esteele]

- Added Plone 4.3 upgrade step to re-install plone.app.theming (Diazo theme
  support) if installed previously. This will upgrade the control panel to the
  new unified one.
  [optilude]

- Added Plone 4.3 upgrade step to make sure TinyMCE 1.3 upgrade steps are run.
  [davisagli]

- Added upgrade step for new sortable_title logic.
  [hannosch]

- Add 'displayPublicationDateInByline' property to site properties sheet.
  Required for PLIP #8699.
  [vipod]

- Remove the plone_deprecated skin layer from all skins in Plone 4.3.
  [davisagli]

- Provide kupu tool module alias, so upgrade steps can read data from it.
  [hannosch]

- Remove kupu from the test dependencies.
  [hannosch]

- Make the RAM cache utility upgrade work without zope.app.cache.
  [davisagli]

- Fix an issue in an old upgrade step when used with current
  ResourceRegistries.
  [davisagli]

- Add Member role to View dashboard permission
  [gaudenz]

- Install plone.app.search when upgrading.
  [esteele]

- Plone 4.1.5 upgrade step added that makes sure that plone.app.discussion
  has been properly installed.
  [timo]

1.2.5 (2013-03-05)
------------------

- Add upgrade profile for Plone 4.2.5
  [esteele]


1.2.4 (2013-01-17)
------------------

- Add upgrade profile for Plone 4.2.4
  [esteele]

- Add missing to_423 folder.
  [esteele]


1.2.3 (2012-12-15)
------------------

- Add upgrade profile for Plone 4.2.3
  [esteele]

- In the UID index migration, if there are items whose key is None,
  skip them instead of complaining about there being multiple items.
  [davisagli]


1.2.2 (2012-10-15)
------------------

- Add upgrade step to make sure the registry record for ResourceRegistries
  bundles is installed.
  [davisagli]


1.2.1 (2012-08-11)
------------------

- Add upgrade profile for Plone 4.2.1
  [esteele]


1.2 (2012-06-29)
----------------

- Add upgrade step to install the CMFEditions component registry bases
  modifier.
  [rossp]


1.2rc2 (2012-05-31)
-------------------

- Add profile for Plone 4.2rc2
  [esteele]


1.2rc1 (2012-05-07)
-------------------

- Fix an issue in an old upgrade step when used with current
  ResourceRegistries.
  [davisagli]

- Add Member role to View dashboard permission
  [gaudenz]

- Install plone.app.search when upgrading.
  [esteele]

- Plone 4.1.5 upgrade step added that makes sure that plone.app.discussion
  has been properly installed.
  [timo]


1.2b2 (2012-02-09)
------------------

- Fix adding Site Administrator roles for when
  custom workflows might not have the permission_roles
  for states set.
  [vangheem]


1.2b1 (2011-12-05)
------------------

- Avoid 4020->4100 rules being overpassed from a 4022 version.
  [tdesvenain]

- Add upgrade step to re-enable the getObjPositionInParent index in the
  portal_atcttool.
  [davisagli]

- Add upgrade step to add Site Administrator to allowRolesToAddKeywords.
  [esteele]

1.2a2 - 2011-08-25
------------------

- Release 1.2a2
  [esteele]


1.2a1 - 2011-08-08
------------------

- Removed input-label.js from portal_javascript in the 4.2 alpha profile.
  [spliter]


1.1.7 (2012-06-27)
------------------

- Add Plone 4.1.6 upgrade step.
  [esteele]


1.1.6 (2012-04-18)
------------------

- Add Plone 4.1.5 upgrade step.
  [esteele]


1.1.5 (2012-02-08)
------------------

- Fix adding Site Administrator roles for when
  custom workflows might not have the permission_roles
  for states set.
  [vangheem]


1.1.4 (2011-11-28)
------------------

- Avoid 4020->4100 rules being overpassed from a 4022 version.
  [tdesvenain]


1.1.3 (2011-10-08)
------------------

- Add upgrade step to re-enable the getObjPositionInParent index in the
  portal_atcttool.
  [davisagli]


1.1.2 (2011-09-22)
------------------

- Add missing upgrade steps from recent versions of Plone 4.0.x.
  [davisagli]


1.1.1 (2011-09-21)
------------------

- Fix v41.alphas.convert_to_uuidindex() to truly ignore acquired
  UID values in the index instead of accidentally treating them
  as duplicates, due to a bug in path comparison. Fixes for
  cases where multiple items without UID() method are contained
  in a folder with a UID in a site being upgraded to 4.1:
  http://dev.plone.org/plone/ticket/12185

- Add upgrade step to fix ZCTextIndex OkapiIndex instances with an
  incorrect _totaldoclen
  [davisagli]

- Migrate type icons from content_icon to icon_expr for all FTIs.
  Closes http://dev.plone.org/plone/ticket/12046.
  [thomasdesvenain, vincentfretin]


1.1 - 2011-07-12
----------------

- Fix misnamed metadata.xml files in the 4.1 profiles.
  [esteele]

- Add new upgrade step to add missing UUIDs to Collection-criteria.
  Fixes http://dev.plone.org/plone/ticket/11904.
  [WouterVH]


1.1rc3 - 2011-06-02
-------------------

- In actions.xml, use object_url for the object_buttons.
  Fixes http://dev.plone.org/plone/ticket/11733.
  [WouterVH]

- Actually register the `update_controlpanel_permissions` and
  `update_role_mappings` upgrade steps.
  [hannosch]


1.1rc2 - 2011-05-21
-------------------

- Release 1.1rc2.
  [esteele]


1.1rc1 - 2011-05-20
-------------------

- Adjusted boolean index conversion to new variable index value support
  introduced in ZCatalog 2.13.14.
  [hannosch]

- Added upgrade step to respect the new blacklisted interface list.
  [hannosch]

- Added upgrade step to fix the cataloged ids of interfaces in the
  `object_provides` index. Closes http://dev.plone.org/plone/ticket/11032.
  [hannosch]

- Added new upgrade step to optimize date range index and respect the new
  floor and ceiling date settings.
  [hannosch]

- Removed `v40.alphas.optimizeDateRangeIndexes` upgrade step, as it is
  superseded by the `v41.alphas.optimize_rangeindex` code and would do an
  upgrade that the second step reverted anyways.
  [hannosch]

- Add MANIFEST.in.
  [WouterVH]

- Remove unexistant GenericSetup step dependency on plonepas-content.
  [kiorky]


1.1b2 - 2011-04-06
------------------

- Added a 4.1b2 profile.
  [esteele]


1.1b1 - 2011-03-02
------------------

- Fix handling of BTrees sets when converting the UUIDIndex.
  [rossp]

- Optimize `DateIndex._unindex` internals.
  [hannosch]


1.1a3 - 2011-02-14
------------------

- Upgrade `UID` index to new UUIDIndex.
  [hannosch]

- Upgrade `is_default_page` and `is_folderish` to new boolean index.
  [hannosch]

- Upgrade index internals for field, key and range indexes.
  [hannosch]

- Added 4.1a3 profile.
  [esteele]


1.1a2 - 2011-02-10
------------------

- Added 4.1a2 steps.
  [esteele]


1.1a1 - 2011-01-18
------------------

- Add CMFPlacefulWorkflow, kupu, iterate and p.a.openid to test dependencies
  as the test site zexps contain their objects.
  [elro]

- Make CMFPlacefulWorkflow, kupu and iterate optional during CMFPlone tests.
  [elro]

- Depend on ``Products.CMFPlone`` instead of ``Plone``.
  [elro]

- Added upgrade step to install plone.outputfilters.
  [davisagli]

- Added properties / actions for Single Sign On login form.
  [elro]

- Added upgrade steps to add the Site Administrator role and Site Administrators
  group and update control panel permissions on upgrading to Plone 4.1a1.
  [davisagli]

- Added infrastructure for upgrades to Plone 4.1.
  [davisagli]


1.0.4 - 2011-02-26
------------------

- Add empty profile for 4.0.3-4.0.4 upgrade.
  [esteele]


1.0.3 - 2011-01-18
------------------

- Add empty profile for 4.0.2-4.0.3 upgrade.
  [esteele]


1.0.2 - 2010-11-15
------------------

- During the blob migration of files and images, disable link
  integrity checking, as it can lead to problems, even though no
  content is permanently removed.
  Fixes http://dev.plone.org/plone/ticket/10992
  and   http://dev.plone.org/plone/ticket/11167
  [maurits]


1.0.1 - 2010-09-28
------------------

- Add empty profile for 4.0-4.0.1 upgrade.
  [esteele]

- Avoid relying on the ``Control_Panel/Products`` section, as it is no longer
  used. This closes http://dev.plone.org/plone/ticket/10824.
  [hannosch]


1.0 - 2010-08-28
----------------

- Add empty profile for rc1-final upgrade.
  [esteele]


1.0rc1 - 2010-08-05
-------------------

- Update personal preferences action to its new URL.
  [davisagli]

- Added `padding-left` to the safe_html style whitelist. This refs
  http://dev.plone.org/plone/ticket/10557.
  [hannosch]

- Update license to GPL version 2 only.
  [hannosch]


1.0b5 - 2010-07-07
------------------

- Added upgrade step to remove the ``sunburst_js`` skin layer.
  [hannosch]

- Upgrade step for removing IE8.js from Sunburst.
  [spliter]

- Merged the ``recompilePythonScripts`` upgrade step with the unified folder
  upgrade step. This avoids an extra complete traversal of the entire site.
  [hannosch]

- Rewrote the ``updateIconMetadata`` upgrade step for speed.
  [hannosch]

- Moved the code to remove old persistent Interface records into the
  recompilePythonScripts step. This step actually covers all objects.
  [hannosch]

- Optimized the ``optimizeDateRangeIndexes`` upgrade step to take advantage of
  knowledge about index internals instead of a brute force reindexIndex call.
  [hannosch]

- Optimized the "update getIcon metadata" upgrade step and added a progress
  handler to it.
  [hannosch]

- Enhance the unregisterOldSteps upgrade step, by removing all persistent
  steps for which a ZCML steps exists.
  [hannosch]

- Take a savepoint before starting the unified folder upgrade. This lets us
  fail fast if there's problems pickling anything.
  [hannosch]

- Also catch TypeError's in the action icons upgrade.
  [hannosch]

- Added optional CacheFu uninstallation step. This will remove CacheFu tools
  if they are detected to be broken.
  [hannosch]

- Removing action links from Events, since they are in the template (and were
  never supposed to have actions in the first place). This fixes
  http://dev.plone.org/plone/ticket/10540.
  [limi]

- Re-add the File and Image FTI icon expressions.
  [davisagli]

- Add missing upgrade steps for control panels and site properties.
  Fixes http://dev.plone.org/plone/ticket/10360
  [davisagli]

- Modify the restoreTheme upgrade step to improve handling of themes when
  upgrading from Plone 3. Now if the skin was "Plone Default", it will be
  set to "Plone Classic Theme" if the layers were uncustomized.  If the
  layers were customized, the layers and viewlet settings will be copied to
  a new skin called "Old Plone 3 Custom Theme", and then "Plone Default"
  will be reset to its typical configuration in a fresh Plone 4 site.
  This closes http://dev.plone.org/plone/ticket/10399
  [davisagli]


1.0b4 - 2010-06-03
------------------

- Add ++resource++plone.app.jquerytools.form.js to jsregistry to accomodate
  new jQuery Forms plug in.
  http://dev.plone.org/plone/ticket/10603
  [smcmahon]

- Add upgrade step to convert all files and images to blobs. This closes
  http://dev.plone.org/plone/ticket/10366.
  [hannosch]

- Upgrade the standard File and Image FTI's to use blobs. This refs
  http://dev.plone.org/plone/ticket/10366.
  [hannosch]

- Add upgrade step to remove the Large Plone Folder type for Plone 4.0rc1
  (there is another step which already turns Large Plone Folders into
  unordered regular Folders). Removed references to Large Plone Folder from
  old upgrade steps.
  [davisagli]


1.0b3 - 2010-05-03
------------------

- Added an automated upgrade step to remove old persistent Zope2 Interface
  records. This refs http://dev.plone.org/plone/ticket/10446.
  [dunlapm, hannosch]


1.0b2 - 2010-04-09
------------------

- Add an upgrade step to update the getIcon metadata column for core types so
  that our new CSS sprited icons can be used.
  [esteele]

- Update the safe_html transform with the new config params, migrating existing
  config from Kupu.
  [elro]

- Added upgrade step for viewlet changes in Plone 4.0b2.
  [davisagli]


1.0b1 - 2010-03-08
------------------

- Update the Plone 4 action icons upgrade step to avoid storing icon
  expressions as unicode when possible.
  [davisagli]

- Add step to update viewlet order and hidden managers for the Sunburst theme
  to reflect recent changes.
  [davisagli]

- Add upgrade step to move added recursive_groups plugin to the bottom of the
  IGroupsPlugin list.
  [esteele]

- Added upgrade step to profile version 4007.
  [hannosch]


1.0a5 - 2010-02-19
------------------

- Migrate `getObjPositionInParent` to stub index capable of sorting search
  results according to their position in the container, a.k.a. "nogopip".
  [witsch]

- In migration to 4.0a5, hide the plone.path_bar viewlet from the
  plone.portaltop manager for the Sunburst Theme.
  [davisagli]

- Add new editing control panel.
  [hannosch]

- Removed the no longer needed history viewlet. This refs
  http://dev.plone.org/plone/ticket/10102.
  [hannosch]

- Added upgrade step to update folderish types to add the 'All content'
  folder_full_view. Include IE fixes and disabling of base2 js.
  [elro]

- Add upgrade step to cleanup plonetheme.classic CSS resources upon
  migration. Make plonetheme.classic visible in the QI.
  Refs http://dev.plone.org/plone/ticket/9988.
  [dukebody]

- Added upgrade step to optimize the internal data structures of date range
  indexes as introduced in Zope 2.12.2.
  [hannosch]

- Changed the cleanUpProductRegistry upgrade step to remove all entries from the
  persistent registry and run it again for existing alpha sites.
  [hannosch]


1.0a4 - 2010-02-01
------------------

- Fix theme upgrades by making sure that plone_styles gets updated to
  classic_styles even when it already exists in the skins tool.
  [davisagli]

- Add upgrade step to create, but not install, a recursive groups PAS plugin.
  [esteele]

- Update the `portal_type` of former "Large Folder" content to "Folder".
  Refs http://dev.plone.org/plone/ticket/9791.
  [witsch]

- Make sure the step registry gets cleaned up before the toolset-fixing
  profile gets imported, when upgrading to 4.x.
  [davisagli]

- Add upgrade to pull iefixes from ResourceRegistries.
  Refs http://dev.plone.org/plone/ticket/9278.
  [dukebody]

- Add missing upgrades from Plone 3.3.2 to 3.3.3 to 3.3.4 to 4.0a1.
  [davisagli]

- Call the portal_metadata DCMI upgrade step from CMFDefault when upgrading
  to Plone 4.0b1.
  [davisagli]

- Enable the diff export in functional upgrade tests, we do a complete
  GenericSetup export of all upgraded sites now.
  [hannosch]

- Remove the hint of doing an export/import comparison for the full upgrades.
  These have varying add-ons installed depending on the original site and its
  quite hard to get the same add-ons installed again in a new site.
  [hannosch]

- Added functional upgrade tests based on an actual zexp export of each major
  version of Plone. Each one is imported and upgraded. A diff of the upgraded
  configuration vs the one of a completely new site is generated. Thanks to
  CMF for the inspiration. This closes http://dev.plone.org/plone/ticket/721.
  [hannosch]

- Declared missing dependencies.
  [hannosch]


1.0a3 - 2009-12-16
------------------

- Updated all profile versions in the Plone 4 series to new simple integer
  based numbers.
  [hannosch]

- Updated to match the new profile version for Plone.
  [hannosch]

- Extended the unregisterOldSteps upgrade step to remove persistent step
  registrations now done via ZCML.
  [hannosch]

- Fixed a reference of jquery.js in the Plone 3.0 upgrade steps. The file was
  only introduced in Plone 3.1.
  [hannosch]

- Moved the join action URL expression update to the 4.0a2-4.0a3 step, since
  it never got wired up for a1-a2.
  [davisagli]

- Removed references to content_icon, which is deprecated in CMFCore 2.2.0
  beta 1.
  [davisagli]


1.0a2 - 2009-12-02
------------------

- Provide join_form_fields to user_registration_fields migration.
  [esteele]

- Recompile all persistent Python Scripts during the upgrade.
  [hannosch]

- Simplify installation of new dependencies and include ``plone.app.imaging``.
  [hannosch]

- Run the steps found in the ``Products.CMFPlone:dependencies`` profile.
  [hannosch]

- Remove ``calendarpopup.js`` from portal_javascripts.
  [hannosch]

- Preserve the default theme after an upgrade instead of making sunburst the
  new default. Also ensure the classic_styles layer isn't part of sunburst.
  [hannosch]

- The plone_styles layer is automatically renamed to classic_styles.
  [hannosch]

- Let the mailhost upgrade step replace broken objects with a fresh standard
  mailhost. It's likely our new one has the features of the custom product.
  [hannosch]

- Clean up Zope's product registry to deal with removed products and internal
  changes to the HelpSys catalogs.
  [hannosch]

- Deal with more removed import steps and remove them from the registry.
  [hannosch]

- Cleanup the skins tools and remove broken directory views as well as cleaning
  up the skin selections to avoid references to no longer existing directories.
  [hannosch]

- Remove entries from the toolset registry pointing to no longer existing
  tools. This can happen when add-ons have been uninstalled.
  [hannosch]

- When upgrading to Plone 4.0a1, be sure to update the toolset with new class
  locations before importing any other profiles, which might otherwise fail
  in the toolset step. Be sure to update the locations for the tools which
  moved from CMFPlone to PlonePAS, for upgrades from very old sites.
  [davisagli]


1.0a1 - 2009-11-17
------------------

- Added Products.contentmigration as a dependency.
  [hannosch]

- Fixed removeal of highlightsearchterms.js.
  [naro]

- Added plonetheme.classic and plonetheme.sunburst as dependencies.
  [naro]

- Add migration for unified folders.
  [witsch]

- Replace highlightsearchterms.js with jquery.highlightsearchterms.js
  [mj]

- Add new default modifiers from CMFEditions on upgrade.
  [alecm]

- Adjust the sarissa.js condition on upgrading to Plone 4, so that it doesn't
  break if kupu is absent.
  [davisagli]

- Make sure the TinyMCE profile and default_editor property get installed when
  upgrading to Plone 4 (kupu remains the default editor for upgraded sites).
  [davisagli]

- Aded Migration for SecureMailHost removal
  [alecm]

- Added step to remove the plone_various step from the persistent import
  step registry.
  [davisagli]

- Added upgrade step to remove outdated actions and properties from both the
  Plone Site and TempFolder FTI.
  [hannosch]

- Adjusted setupReferencebrowser upgrade step to proper new-style.
  [hannosch]

- Added property use_email_as_login=False to the site properties in the
  Plone 4 alpha migration. Refs http://dev.plone.org/plone/ticket/9214.
  [maurits]

- Added update of resources to use the authenticated flag instead of a full
  expression where possible, in the Plone 4 alpha migration.
  [davisagli]

- Added renaming of Categories to Tags in the portal_atct tool indices in the
  Plone 4 alpha migration.
  [davisagli]

- Added updating of the actor variable expression for several workflows in the
  Plone 4 alpha migration. This helps fix
  http://dev.plone.org/plone/ticket/7398.
  [davisagli]

- Added removal of action for AT graphviz reference visualization from
  all content types in the Plone 4 alpha migration.
  [davisagli]

- Made the action icons migration switch from GIF to PNG where possible,
  and correctly handle actions in the document_actions category.
  [davisagli]

- Added link to upgrade instructions for sites upgraded from Plone < 2.5
  (technically, sites using GroupUserFolder)
  [davisagli]

- Added a INonInstallable utility to hide this package's profiles from the
  quick installer.
  [davisagli]

- Fixed a couple profiles that were not registered for IMigratingPloneSiteRoot.
  [davisagli]

- Added Plone 4 migration step to add icon_expr to FTIs.
  [davisagli]

- Revert the migration steps for getting rid of the external editor.
  [davisagli]

- Adjusted action icon migration to handle the configlet icons properly.
  [davisagli]

- Re-added missing configlet migrations.
  [davisagli]

- Adjust migration for installing CMFDiffTool to reflect the fact that this is
  now configured in CMFPlone.
  [davisagli]

- Re-add portal_controlpanel to the list of special action providers for the
  migrateOldActions function.
  [davisagli]

- Corrected the migrateActionIcons function to use the correct API for setting
  the new icon_expr, so that the icon_expr_object also gets set correctly.
  [davisagli]

- Adjusted the addMissingWorkflows action to reflect additional variables
  returned by the WorkflowDefinitionConfigurator in current DCWorkflow.
  [davisagli]

- Moved the cleanDefaultCharset action to the 3.0a2-3.0b1 migration; it is a
  prerequisite for that step's properties.xml import.
  [davisagli]

- Adjusted the 2.5-3.0a1 step to correct the toolset registry class metadata
  for the tools which are located in PlonePAS as of Plone 3.
  [davisagli]

- Added migration to make sure we're using an IRAMCache utility from
  zope.ramcache instead of zope.app.cache
  [davisagli]

- Merged changeset 27805 from 3.3 branch migrations for 3.3rc3 to
  3.3rc4 (fix cooked expressions in css registry).
  [maurits]

- Added the z3c.autoinclude entry point so this package is automatically loaded
  on Plone 3.3 and above.
  [hannosch]

- Import the `replace_local_role_manager` method from borg.localrole.
  [hannosch]

- Merge changeset 24257 from 3.2 branch migrations for 3.2 to 3.2.1
  [calvinhp]

- Fixed deprecation warnings for use of Globals.
  [hannosch]

- Specified package dependencies.
  [hannosch]

- Updated method calls to PlonePAS. They lost the out argument.
  [hannosch]

- Adjusted enableZope3Site function to match the new CMF21 upgrade step.
  [hannosch]

- Removed safeGetMemberDataTool method, which wasn't used anywhere.
  [hannosch]

- Initial implementation.
  [hannosch]
