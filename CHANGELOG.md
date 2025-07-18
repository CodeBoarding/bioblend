## BioBlend v1.6.0 - 2025-06-18

* Added support for Galaxy release 25.0.

* Added support for API auth with access token (thanks to
  [Nuwan Goonasekera](https://github.com/nuwang)).

* Added ``decode_id()`` and ``encode_id()`` methods to ``ConfigClient`` (thanks
  to [Simon Bray](https://github.com/simonbray)).

* Added ``get_invocation_archive()`` method to ``InvocationClient`` (thanks to
  [Patrik Smeds](https://github.com/Smeds)).

* Added ``instance`` and ``legacy`` parameters to
  ``WorkflowClient.show_workflow()`` (thanks to
  [Patrik Smeds](https://github.com/Smeds)).

* Improvements to documentation, tests and type annotation (thanks to
  [Dannon](https://github.com/dannon) and
  [Matthias Bernt](https://github.com/bernt-matthias)).

### BioBlend v1.5.0 - 2025-03-06

* Dropped support for Python 3.8. Added support for Galaxy release 24.2.

* Added ``limit``, ``offset`` and ``include_deleted`` parameters to
  ``FoldersClient.show_folder()`` (thanks to
  [Matthias Bernt](https://github.com/bernt-matthias)).

* Added ``offset`` parameter to ``InvocationClient.get_invocations()`` and
  BioBlend.objects ``ObjInvocationClient.list()`` methods.

* Added ``quota_source_label`` parameter to ``QuotaClient.create_quota()``
  (thanks to [Matthias Bernt](https://github.com/bernt-matthias)).

* Added ``style`` parameter to ``WorkflowClient.export_workflow_dict()`` method
  (thanks to [Marius van den Beek](https://github.com/mvdbeek)).

* Improvements to type annotations and documentation.

### BioBlend v1.4.0 - 2024-11-06

* Added support for Python 3.13. Added support for Galaxy release 24.1.

* Added ``user_agent`` parameter to the ``__init__()`` method of the
  ``GalaxyClient``, ``GalaxyInstance`` and ``ToolShedInstance`` classes (thanks
  to [Daniel Blankenberg](https://github.com/blankenberg)).

* Added ``version`` and ``use_cached_job`` parameters to
  ``WorkflowClient.invoke_workflow()`` method (reported by
  [Bérénice Batut](https://github.com/bebatut)).

* Changed the default values for the ``operation`` and ``default`` parameters of
  the ``QuotaClient.update_quota()`` method (thanks to
  [Matthias Bernt](https://github.com/bernt-matthias)).

* Improvements to tests and documentation (thanks to
  [Matthias Bernt](https://github.com/bernt-matthias)).

### BioBlend v1.3.0 - 2024-05-12

* Dropped support for Python 3.7. Added support for Python 3.12. Added support
  for Galaxy releases 23.2 and 24.0.

* Added ``copy_elements`` parameter to
  ``HistoryClient.create_dataset_collection()`` and BioBlend.objects
  ``History.create_dataset_collection()`` methods.

* Added ``wait`` parameter to ``HistoryClient.delete_dataset()`` and
  BioBlend.objects ``HistoryDatasetAssociation.delete()`` methods.

* Added ``create_time_min``, ``create_time_max``, ``update_time_min``,
  ``update_time_max``, ``view``, ``keys``, ``limit`` and ``offset`` parameters
  to ``HistoryClient.get_histories()`` (thanks to
  [cat-bro](https://github.com/cat-bro)).

* Added ``create_time_min``, ``create_time_max``, ``update_time_min`` and
  ``update_time_max`` parameters to ``HistoryClient.get_published_histories()``
  (thanks to [cat-bro](https://github.com/cat-bro)).

* Added ``keys`` parameter to ``HistoryClient.show_history()`` (thanks to
  [cat-bro](https://github.com/cat-bro)).

* Dropped broken ``deleted`` parameter of ``DatasetClient.show_dataset()``.

* Parameters after ``password`` in the ``__init__()`` method of the
  ``GalaxyClient``, ``GalaxyInstance`` and ``ToolShedInstance`` classes are now
  keyword-only.

* Classes defined in ``bioblend.galaxy.objects.wrappers`` are no more
  re-exported by ``bioblend.galaxy.objects``.

* ``DatasetTimeoutException`` and ``DatasetCollectionTimeoutException`` are now
  aliases for ``TimeoutException`` instead of subclasses.

* Added support for the new "cancelling" invocation state.

* Fixed ``InvocationClient.get_invocation_biocompute_object()`` method on
  upcoming Galaxy 24.1 .

* Improvements to linting and tests (thanks to
  [Matthias Bernt](https://github.com/bernt-matthias)).

### BioBlend v1.2.0 - 2023-06-30

* Dropped support for Galaxy releases 17.09-19.01. Added support for Galaxy
  release 23.1.

* Added a new ``container_resolution`` attribute to ``GalaxyInstance`` objects,
  which is an instance of the new ``ContainerResolutionClient``. This new module
  can be used to list container resolvers, and to resolve (and install) tool
  requirements against specified container resolvers (thanks to
  [cat-bro](https://github.com/cat-bro) and
  [Matthias Bernt](https://github.com/bernt-matthias)).

* Added ``reload_toolbox()`` method to ``ConfigClient`` (thanks to
  [Anthony Bretaudeau](https://github.com/abretaud)).

* Added ``delete_unused_dependency_paths()`` and ``unused_dependency_paths()``
  methods to ``ToolDependenciesClient`` (thanks to
  [Matthias Bernt](https://github.com/bernt-matthias)).

* Added ``data_manager_mode`` parameter to ``ToolClient.run_tool()`` method
  (thanks to [Marius van den Beek](https://github.com/mvdbeek)).

* Added ``user_data`` parameter to ``UserClient.update_user()`` method
  (thanks to [Uwe Winter](https://github.com/uwwint)).

* Fixed bug in ``DatasetClient.download_dataset()`` and BioBlend.objects
  ``HistoryDatasetAssociation.get_stream()`` where the wrong download URL was
  generated if the Galaxy instance is served at a subdirectory (reported by
  [Anil Thanki](https://github.com/anilthanki)).

* Improvements to tests and documentation (thanks to
  [kxk302](https://github.com/kxk302) and
  [Simon Bray](https://github.com/simonbray)).

### BioBlend v1.1.1 - 2023-02-21

* Same as BioBlend v1.1.0, briefly released with wrong version number 1.0.1 on
  GitHub, PyPI and Bioconda.

* Added support for Python 3.11. Added support for Galaxy release 23.0.

* Using the deprecated ``folder_id`` parameter of the
  ``LibraryClient.get_folders()`` method now raises a ``ValueError`` exception.

* Using the deprecated ``library_id`` parameter of the
  ``LibraryClient.get_libraries()`` method now raises a ``ValueError``
  exception.

* Using the deprecated ``tool_id`` parameter of the ``ToolClient.get_tools()``
  method now raises a ``ValueError`` exception.

* Using the deprecated ``workflow_id`` parameter of the
  ``WorkflowClient.get_workflows()`` method now raises a ``ValueError``
  exception.

* Modified ``delete_workflow()`` method of ``WorkflowClient`` to return
  ``None`` instead of a string.

* Added ``py.typed`` marker file to distributed packages (as per PEP 561) to
  declare type checking support.

* Improvements to tests and documentation.

### BioBlend v1.0.0 - 2022-10-13

* Dropped support for deprecated CloudMan, see
  https://galaxyproject.org/blog/2021-10-sunsetting-cloudlaunch/

* Added dependency on ``typing-extensions`` package, removed dependencies on
  ``boto`` and ``pyyaml``.

* Deprecated ``max_get_retries()``, ``set_max_get_retries()``,
  ``get_retry_delay()`` and ``set_get_retry_delay()`` methods of ``Client``.

* Moved ``max_get_attempts`` and ``get_retry_delay`` properties from
  ``GalaxyInstance`` to ``GalaxyClient``, so they are also available in
  ``ToolshedInstance``.

* Added ``get_or_create_user_apikey()`` method to ``UserClient``.

* Added ``all`` parameter to ``HistoryClient.get_histories()`` method (thanks to
  [Paprikant](https://github.com/Paprikant)).

* Added ``require_exact_tool_versions`` parameter to
  ``WorkflowClient.invoke_workflow()`` method (thanks to
  [cat-bro](https://github.com/cat-bro)).

* Added ``name`` and ``owner`` parameters to
  ``ToolShedRepositoryClient.get_repositories()``.

* Remove unused methods from ``bioblend.config.Config``. If needed, use the
  methods inherited from `configparser.ConfigParser` instead.

* Allowed any 2XX HTTP response status code in ``Client._delete()`` to correctly
  support history purging via Celery (thanks to
  [Nolan Woods](https://github.com/innovate-invent)).

* Fixed bug in ``FormsClient.create_form()`` where the ``form_xml_text``
  argument was not passed correctly to the Galaxy API.

* Fixed bug in ``HistoryClient.show_dataset_provenance()`` where the ``follow``
  argument was not passed to the Galaxy API.

* BioBlend.objects: Added ``delete()`` abstract method to ``DatasetContainer``
  class.

* Added Code of Conduct for the project.

* Finished the full type annotation of the library (thanks to
  [cat-bro](https://github.com/cat-bro),
  [Fabio Cumbo](https://github.com/cumbof),
  [Jayadev Joshi](https://github.com/jaidevjoshi83),
  [thepineapplepirate](https://github.com/thepineapplepirate)).

* Improvements to tests and documentation.

### BioBlend v0.18.0 - 2022-07-07

* Added support for Galaxy release 22.05.

* Added tus support to ``ToolClient.upload_file()`` (thanks to
  [Nate Coraor](https://github.com/natefoo)).

* Formatted Python code with black and isort.

* Improvements to type annotations, tests and documentation.

### BioBlend v0.17.0 - 2022-05-09

* Dropped support for Python 3.6. Added support for Python 3.10. Added support
  for Galaxy releases 21.09 and 22.01.

* Removed deprecated ``run_workflow()`` method of ``WorkflowClient``.

* Using the deprecated ``history_id`` parameter of the
  ``HistoryClient.get_histories()`` method now raises a ``ValueError``
  exception.

* Made ``tool_inputs_update`` parameter of ``JobsClient.rerun_job()`` more
  flexible.

* Added ``whoami()`` method to ``ConfigClient`` (thanks to
  [cat-bro](https://github.com/cat-bro)).

* Added ``get_extra_files()`` method to ``HistoryClient``.

* Added ``build()`` and ``reload()`` methods to ``ToolClient`` (thanks to
  [Jayadev Joshi](https://github.com/jaidevjoshi83) and
  [cat-bro](https://github.com/cat-bro) respectively).

* Added ``get_repositories()`` method to ``ToolShedCategoryClient`` (thanks to
  [cat-bro](https://github.com/cat-bro)).

* Added ``update_repository_metadata()`` method to ``ToolShedRepositoryClient``.

* Added ``order_by`` parameter to ``JobsClient.get_jobs()`` method.

* BioBlend.objects: Removed deprecated ``run()`` method of ``Workflow``.

* BioBlend.objects: Fail if multiple libraries/histories/workflows match when
  deleting by name, instead of deleting them all.

* BioBlend.objects: in ``HistoryDatasetAssociation.get_stream()``, wait for
  the dataset to be ready.

* BioBlend.objects: in ``Workflow.invoke()``, check that the workflow is mapped
  and runnable before invoking, allow the ``inputs`` parameter to be an instance
  of a ``Dataset`` subclass, and allow the ``history`` parameter to be the name
  of a new history.

* BioBlend.objects: Added new ``datasets`` and ``dataset_collections``
  attributes to ``GalaxyInstance`` objects, which are instances of the new
  ``ObjDatasetClient`` and ``ObjDatasetCollectionClient`` respectively.

* BioBlend.objects: Added ``refresh()``, ``get_outputs()`` and
  ``get_output_collections()`` methods to ``InvocationStep``.

* Fixed [error](https://github.com/galaxyproject/bioblend/issues/398) when
  instantiating ``GalaxyInstance`` with ``email`` and ``password`` (reported by
  [Peter Briggs](https://github.com/pjbriggs)).

* Fixed parameter validation errors for POST requests with attached files on
  upcoming Galaxy 22.05.

* Code cleanups (thanks to [Martmists](https://github.com/Martmists-GH)).

* Improvements to type annotations, tests and documentation.

### BioBlend v0.16.0 - 2021-06-13

* Added support for Galaxy release 21.05.

* Replaced the ``job_info`` parameter with separate ``tool_id``, ``inputs`` and
  ``state`` parameters in ``JobsClient.search_jobs()`` (thanks to
  [rikeshi](https://github.com/rikeshi)).

* Pass the API key for all requests as the ``x-api-key`` header instead of as a
  parameter (thanks to [rikeshi](https://github.com/rikeshi)).

* Try prepending "https://" and "http://" if the scheme is missing in the
  ``url`` argument passed to ``GalaxyClient``, i.e. when initialising a Galaxy
  or ToolShed instance.

* Added a new ``dataset_collections`` attribute to ``GalaxyInstance`` objects,
  which is an instance of the new ``DatasetCollectionClient``. This new module
  can be used to get details of a dataset collection, wait until elements of a
  dataset collection are in a terminal state, and download a history dataset
  collection as an archive (thanks to [rikeshi](https://github.com/rikeshi)).

* Added a new ``tool_dependencies`` attribute to ``GalaxyInstance`` objects,
  which is an instance of the new ``ToolDependenciesClient``. This new module
  can be used to summarize requirements across toolbox (thanks to
  [cat-bro](https://github.com/cat-bro)).

* Added ``publish_dataset()`` ``update_permissions()`` and
``wait_for_dataset()`` methods to ``DatasetClient``.

* Added ``get_invocation_biocompute_object()``, ``get_invocation_report_pdf()``,
  ``get_invocation_step_jobs_summary()``, ``rerun_invocation()`` and
  ``wait_for_invocation()`` methods to ``InvocationClient`` (thanks to
  [rikeshi](https://github.com/rikeshi)).

* Added ``cancel_job()``, ``get_common_problems()``,
  ``get_destination_params()``, ``get_inputs()``, ``get_outputs()``,
  ``resume_job()``, ``show_job_lock()``, ``update_job_lock()`` and
  ``wait_for_job()`` methods to ``JobsClient`` (thanks to
  [Andrew Mcgregor](https://github.com/Mcgregor381) and
  [rikeshi](https://github.com/rikeshi)).

* Added ``get_citations()`` and ``uninstall_dependencies()`` methods to
  ``ToolClient`` (thanks to [rikeshi](https://github.com/rikeshi)).

* Added ``extract_workflow_from_history()``, ``refactor_workflow()`` and
  ``show_versions()`` methods to ``WorkflowClient`` (thanks to
  [rikeshi](https://github.com/rikeshi)).

* Added several parameters to ``DatasetClient.get_datasets()`` method (thanks to
  [rikeshi](https://github.com/rikeshi)).

* Added several parameters to ``InvocationClient.get_invocations()`` method
  (thanks to [Nolan Woods](https://github.com/innovate-invent) and
  [rikeshi](https://github.com/rikeshi)).

* Added several parameters to ``JobsClient.get_jobs()`` method (thanks to
  [rikeshi](https://github.com/rikeshi)).

* Added ``parameters_normalized`` parameter to
  ``WorkflowClient.invoke_workflow()`` method (thanks to
  [rikeshi](https://github.com/rikeshi)).

* Deprecated ``folder_id`` parameter of ``LibraryClient.get_folders()`` method.

* Deprecated ``library_id`` parameter of ``LibraryClient.get_libraries()``
  method.

* Deprecated ``tool_id`` parameter of ``ToolClient.get_tools()`` method.

* Deprecated ``workflow_id`` parameter of ``WorkflowClient.get_workflows()``
  method.

* BioBlend.objects: Removed deprecated ``container_id`` property of ``Dataset``
  and ``Folder`` objects.

* BioBlend.objects: Removed ``Preview`` abstract class.

* BioBlend.objects: Added ``invoke()`` method to ``Workflow``. Added
  ``ObjInvocationClient``, and ``Invocation`` and ``InvocationPreview`` wrappers
  (thanks to [rikeshi](https://github.com/rikeshi)).

* BioBlend.objects: Added ``latest_workflow_uuid`` property to ``Workflow``
  objects. Added ``deleted``, ``latest_workflow_uuid``, ``number_of_steps``,
  ``owner`` and ``show_in_tool_panel`` properties to ``WorkflowPreview`` (thanks
  to [Nolan Woods](https://github.com/innovate-invent)).

* BioBlend.objects: Deprecated ``run()`` method of ``Workflow``.

* Added ``use_ssl``, ``verify`` and ``authuser`` parameters to
  ``CloudManInstance.__init__()`` (thanks to
  [Nathan Edwards](https://github.com/edwardsnj)).

* Improvements to type annotations, tests and documentation (thanks to
  [rikeshi](https://github.com/rikeshi)).

### BioBlend v0.15.0 - 2021-02-10

* Dropped support for Python 3.5. Added support for Python 3.9. Added support
  for Galaxy releases 20.09 and 21.01.

* Changed the return value of ``RolesClient.create_role()`` method from a
  1-element list containing a dict to a dict.

* Removed deprecated ``download_dataset()`` and ``get_current_history``
  methods of ``HistoryClient``.

* Removed deprecated ``export_workflow_json()`` and ``import_workflow_json``
  methods of ``WorkflowClient``.

* Added ``copy_content()``, ``get_published_histories()`` and ``open_history()``
  methods to ``HistoryClient``.

* Added ``rerun_job()`` method to ``JobsClient``.

* Added ``requirements()`` method to ``ToolClient`` (thanks to
  [cat-bro](https://github.com/cat-bro)).

* Added ``published`` and ``slug`` parameters to
  ``HistoryClient.get_histories()``.

* Added ``require_state_ok`` parameter to ``DatasetClient.download_dataset()``.

* Added ``input_format`` parameter to ``ToolClient.run_tool()``.

* Deprecated ``history_id`` parameter of ``HistoryClient.get_histories()``
  method.

* BioBlend.objects: Added ``owner`` property to ``Workflow`` objects. Added
  ``annotation``, ``published`` and ``purged`` properties to ``HistoryPreview``
  objects.

* Fixed issue where specifying the Galaxy URL with "http://" instead of
  "https://" when creating a ``GalaxyInstance`` made the subsequent non-GET
  requests to silently fail.

* Moved the Continuous Integration (CI) from TravisCI to GitHub workflows
  (thanks to [Oleg Zharkov](https://github.com/OlegZharkov)).

* Improvements to tests and documentation (thanks to
  [Gianmauro Cuccuru](https://github.com/gmauro)).

### BioBlend v0.14.0 - 2020-07-04

* Dropped support for Python 2.7. Dropped support for Galaxy releases
  14.10-17.05. Added support for Python 3.8. Added support for Galaxy releases
  19.09, 20.01 and 20.05.

* Added a new ``invocations`` attribute to ``GalaxyInstance`` objects, which is
  an instance of the new ``InvocationClient`` class. This new module can be used
  to get all workflow invocations, show or cancel an invocation, show or pause
  an invocation step, get a summary or a report for an invocation (thanks to
  [Simon Bray](https://github.com/simonbray)).

* Added ``get_datasets()`` method to ``DatasetClient`` (thanks to
  [Simon Bray](https://github.com/simonbray)).

* Added ``import_history()`` method to ``HistoryClient`` (thanks to
  [David Christiany](https://github.com/davidchristiany) and
  [Marius van den Beek](https://github.com/mvdbeek)).

* Added ``copy_dataset()`` method to ``HistoryClient`` (thanks to
  [Simon Bray](https://github.com/simonbray)).

* Added ``get_metrics()`` method to ``JobsClient`` (thanks to
  [Andreas Skorczyk](https://github.com/AndreasSko)).

* Added ``report_error()`` method to ``JobsClient`` (thanks to
  [Peter Selten](https://github.com/selten)).

* Added ``get_dataset_permissions()`` and ``set_dataset_permissions()`` methods
  to ``LibraryClient`` (thanks to
  [Frederic Sapet](https://github.com/FredericBGA)).

* Added ``update_user()`` method to ``UserClient`` (thanks to
  [Anthony Bretaudeau](https://github.com/abretaud)).

* Added ``update_workflow()`` method to ``WorkflowClient``.

* Added ``tags`` parameter to ``upload_file_from_url()``,
  ``upload_file_contents()``, ``upload_file_from_local_path()``,
  ``upload_file_from_server()`` and ``upload_from_galaxy_filesystem()`` methods
  of ``LibraryClient`` (thanks to
  [Anthony Bretaudeau](https://github.com/abretaud)).

* Changed the default for the ``tag_using_filenames`` parameter of
  ``upload_file_from_server()`` and ``upload_from_galaxy_filesystem()`` methods
  of ``LibraryClient`` from ``True`` to ``False`` (thanks to
  [Anthony Bretaudeau](https://github.com/abretaud)).

* Added ``version`` parameter to ``show_workflow()`` and
  ``export_workflow_dict()`` methods of ``WorkflowClient``.

* Added ``inputs_by`` option to ``invoke_workflow()`` method of
  ``WorkflowClient`` (thanks to
  [Marius van den Beek](https://github.com/mvdbeek)).

* Removed deprecated ``show_stderr()`` and ``show_stdout`` methods of
  ``DatasetClient``.

* BioBlend.objects: Allowed workflow steps of type ``parameter_input`` and
  ``subworkflow``. Added ``parameter_input_ids`` property to ``Workflow``
  objects (reported by [Nolan Woods](https://github.com/innovate-invent)).

* Fixed ``HistoryClient.export_history(..., wait=False, maxwait=None)``
  (reported by [David Christiany](https://github.com/davidchristiany)).

* Moved internal ``_make_url()`` method from ``GalaxyClient`` to ``Client``
  class.

### BioBlend v0.13.0 - 2019-08-09

* Dropped support for Python 3.4. Added support for Galaxy releases 19.01 and
  19.05.

* Updated ``requests-toolbelt`` requirement to ``>=0.5.1`` to prevent failing of
  uploads to Galaxy (reported by [m93](https://github.com/mmeier93)).

* Added ``toolshed`` attribute to ``GalaxyInstance`` and made ``toolShed`` an
  alias to it (reported by [Miriam Payá](https://github.com/mpaya)).

* Added ``uninstall_repository_revision()`` method to ``ToolShedClient`` (thanks
  to [Helena Rasche](https://github.com/erasche), reported by
  [Alexander Lenail](https://github.com/alexlenail)).

* Added ``maxwait`` parameter to ``HistoryClient.export_history()`` and
  ``History.export()`` methods.

* Fixed handling of ``type`` argument in ``HistoryClient.show_history()``
  (thanks to [Marius van den Beek](https://github.com/mvdbeek)).

* Fixed handling of ``deleted`` argument in ``LibraryClient.get_libraries()``
  (thanks to [Luke Sargent](https://github.com/luke-c-sargent), reported by
  [Katie](https://github.com/emartchenko)).

* Fixed ``LibraryClient.wait_for_dataset()`` when ``maxwait`` or ``interval``
  arguments are of type ``float``.

* Unify JSON-encoding of non-file parameters of POST requests inside
  ``GalaxyClient.make_post_request()``.

* Improvements to tests and documentation (thanks to
  [Helena Rasche](https://github.com/erasche),
  [Peter Selten](https://github.com/selten) and
  [Pablo Moreno](https://github.com/pcm32)).

### BioBlend v0.12.0 - 2018-12-17

* Added support for Python 3.7. Added support for Galaxy releases 18.05 and
  18.09.

* Added ``update_library_dataset()`` method to ``LibraryClient`` (thanks to
  [Anthony Bretaudeau](https://github.com/abretaud)).

* Added ``preserve_dirs`` and ``tag_using_filenames`` parameters to
  ``upload_file_from_server()`` and ``upload_from_galaxy_filesystem()`` methods
  of ``LibraryClient`` (thanks to
  [Anthony Bretaudeau](https://github.com/abretaud)).

* Removed deprecated ``wait_for_completion`` parameter of
  ``DatasetClient.download_dataset()`` method.

* BioBlend.objects: added ``genome_build`` and ``misc_info`` attributes to
  ``Dataset`` objects. Moved ``deleted`` attribute from ``Dataset`` to
  ``HistoryDatasetAssociation`` and ``LibraryDatasetDatasetAssociation``
  objects. Moved ``purged`` attribute from ``Dataset`` to
  ``HistoryDatasetAssociation`` objects.

* BioBlend.objects: added ``update()`` method to ``LibraryDataset`` (thanks to
  [Anthony Bretaudeau](https://github.com/abretaud)).

* Run tests with pytest instead of nose.

### BioBlend v0.11.0 - 2018-04-18

* Dropped support for Python 3.3. Added support for Galaxy release 18.01.

* Always wait for terminal state when downloading a dataset.

* Deprecated ``wait_for_completion`` parameter of
  ``DatasetClient.download_dataset()`` method.

* Fixed downloading of datasets receiving a HTTP 500 status code (thanks to
  [Helena Rasche](https://github.com/erasche)).

* Added ``wait_for_dataset()`` method to ``LibraryClient``.

* Added ``verify`` parameter to ``GalaxyInstance.__init__()`` method (thanks to
  Devon Ryan).

* Improvements to tests and documentation.

### BioBlend v0.10.0 - 2017-09-26

* Dropped support for Python 2.6. Added support for Galaxy release 17.09.

* Added ``contents`` parameter to ``FoldersClient.show_folder()`` method
  (thanks to [Helena Rasche](https://github.com/erasche)).

* Exposed the `verify` attribute of `GalaxyInstance` and `ToolShedInstance`
  objects as `__init__()` parameter.

* Added ``create_role()`` method to ``RolesClient`` (thanks to Ashok
  Varadharajan).

* Added ``timeout`` parameter to ``GalaxyClient.__init__()`` method.

* Added ``publish`` parameter to ``import_workflow_dict()`` and
  ``import_workflow_from_local_path()`` methods of ``WorkflowClient`` (thanks to
  Marco Enrico Piras).

* BioBlend.objects: added ``publish`` parameter to
  ``ObjWorkflowClient.import_new()`` method (thanks to Marco Enrico Piras).

* Do not check for mismatching content size when streaming a dataset to file
  (reported by Jorrit Boekel).

* Fixed delete requests when Galaxy uses external authentication (thanks to
  [Helena Rasche](https://github.com/erasche)).

* Fixed retrieval of the API key when a ``GalaxyClient`` object is initialised
  with email and password on Python 3 (thanks to
  [Marius van den Beek](https://github.com/mvdbeek)).

* Documentation improvements.

### BioBlend v0.9.0 - 2017-05-25

* Dropped support for Galaxy releases 14.02, 14.04, 14.06 and 14.08. Added
  support for Python 3.5 and 3.6, and Galaxy releases 16.07, 16.10, 17.01 and
  17.05.

* Deprecated ``import_workflow_json()`` and ``export_workflow_json()`` methods
  of ``WorkflowClient`` in favor of ``import_workflow_dict()`` and
  ``export_workflow_dict()`` (reported by @manabuishii).

* Deprecated ``show_stderr()`` and ``show_stdout()`` methods of
  ``DatasetClient`` in favour of ``JobsClient.show_job()`` with
  ``full_details=True``.

* Added ``install_dependencies()`` method to ``ToolClient`` (thanks to
  [Marius van den Beek](https://github.com/mvdbeek)).

* Added ``reload_data_table()`` method to ``ToolDataClient`` (thanks to
  [Marius van den Beek](https://github.com/mvdbeek)).

* Added ``create_folder()``, ``update_folder()``, ``get_permissions()``,
  ``set_permissions()`` methods to ``FoldersClient`` (thanks to
  [Helena Rasche](https://github.com/erasche)).

* Added ``get_version()`` method to ``ConfigClient`` (thanks to
  [Helena Rasche](https://github.com/erasche)).

* Added ``get_user_apikey()`` method to ``UserClient`` (thanks to
  [Helena Rasche](https://github.com/erasche)).

* Added ``create_quota()``, ``update_quota()``, ``delete_quota()`` and
  ``undelete_quota()`` methods to ``QuotaClient`` (thanks to
  [Helena Rasche](https://github.com/erasche)).

* Added ``purge`` parameter to ``HistoryClient.delete_dataset()`` method.

* Added ``f_email``, ``f_name``, and ``f_any`` parameters to
  ``UserClient.get_users()`` method (thanks to
  [Helena Rasche](https://github.com/erasche)).

* Updated ``WorkflowClient.import_shared_workflow()`` method to use the newer
  Galaxy API request (thanks to @DamCorreia).

* Fixed ``HistoryClient.update_history()`` and ``History.update()`` methods
  when ``name`` argument is not specified.

* Added warning if content size differs from content-length header in
  ``DatasetClient.download_dataset()``.

* BioBlend.objects: added ``purge`` parameter to
  ``HistoryDatasetAssociation.delete()`` method.

* BioBlend.objects: added ``purged`` attribute to ``Dataset`` objects.

* BioBlend.objects: added ``published`` attribute to ``History`` objects.

* Code refactoring, added tests and documentation improvements.

### BioBlend v0.8.0 - 2016-08-11

* Removed deprecated ``create_user()`` method of ``UserClient``.

* Deprecated ``HistoryClient.download_dataset()`` in favor of
  ``DatasetClient.download_dataset()``.

* Modified ``update_dataset()``, ``update_dataset_collection()`` and
  ``update_history()`` methods of ``HistoryClient`` to return the details
  instead of the status code.

* Modified ``update_dataset()``, ``update_dataset_collection()`` and
  ``update_history()`` methods of ``HistoryClient`` to return the details
  instead of the status code.

* Modified ``GalaxyClient.make_put_request()`` to return the decoded response
  content.

* Added ``install_resolver_dependencies`` parameter to
  ``ToolShedClient.install_repository_revision()``, applicable for Galaxy
  release 16.07 and later (thanks to
  [Marius van den Beek](https://github.com/mvdbeek)).

* Improve ``DatasetClient.download_dataset()`` by downloading the dataset in
  chunks when saving to file (thanks to Jorrit Boekel).

* Added ``bioblend.toolshed.categories.ToolShedCategoryClient``;
  renamed ``bioblend.toolshed.repositories.ToolShedClient`` class to
  ``bioblend.toolshed.repositories.ToolShedRepositoryClient``;
  renamed ``bioblend.toolshed.tools.ToolShedClient`` class to
  ``bioblend.toolshed.tools.ToolShedToolClient``.

* Added ``delete_user()`` method to ``UserClient``.

* BioBlend.objects: added ``update()`` method to ``HistoryDatasetAssociation``.

* BioBlend.objects: added ``annotation`` and ``genome_build`` attributes to
  ``HistoryDatasetAssociation`` objects.

* BioBlend.objects: added ``update()`` method to ``HistoryDatasetAssociation``.

* BioBlend.objects: added ability to create and delete dataset collections
  (thanks to Alex MacLean).

* BioBlend.objects: added dataset collections to the outputs of
  ``Workflow.run()``.

* Added ability to launch Galaxy CloudMan instances into AWS VPC.

* A number of testing tweaks, documentation improvements and minor fixes.

### BioBlend v0.7.0 - 2015-11-02

* BioBlend.objects: enabled import of workflows containing dataset collection
  inputs.

* Implemented APIs for a modern Galaxy workflow APIs (i.e. delayed scheduling).

* Implemented APIs to search Tool Shed repositories and tools.

* Added support for uploading (importing) from FTP (thanks to
  [Helena Rasche](https://github.com/erasche)).

* Added ``to_posix_lines`` and ``space_to_tab`` params to ``upload_file()``,
  ``upload_from_ftp()`` and ``paste_content()`` methods of ``ToolClient``.

* BioBlend.objects: added ``upload_from_ftp()`` method to ``History``.

* Updated the testing framework to work with Galaxy wheels; use TravisCI's
  container infrastructure; test Galaxy release 15.07.

* Updated CloudmanLauncher's ``launch`` method to accept ``subnet_id``
  parameter, for VPC support (thanks to Matthew Ralston).

* Properly pass extra arguments to cloud instance userdata.

* Updated placement finding methods and `get_clusters_pd` method to return a
  dict vs. lists so error messages can be included.

* A numer of documentation improvements and minor updates/fixes (see individual
  commits).

### BioBlend v0.6.1 - 2015-07-27

* BioBlend.objects: renamed ``ObjDatasetClient`` abstract class to
  ``ObjDatasetContainerClient``.

* BioBlend.objects: added ``ABCMeta`` metaclass and ``list()`` method to
  ``ObjClient``.

* BioBlend.objects: added ``io_details`` and ``link_details`` parameters to
  ``ObjToolClient.get()`` method.

* Open port 8800 when launching cloud instances for use by NodeJS proxy for
  Galaxy IPython Interactive Environments.

* When launching cloud instances, propagate error messages back to the called.
  The return types for methods ``create_cm_security_group``, ``create_key_pair``
  in ``CloudManLauncher`` class have changed as a result of this.

### BioBlend v0.6.0 - 2015-06-30

* Added support for Python >= 3.3.

* Added ``get_library_permissions()`` method to ``LibraryClient``.

* Added ``update_group()``, ``get_group_users()``, ``get_group_roles()``,
  ``add_group_user()``, ``add_group_role()``, ``delete_group_user()`` and
  ``delete_group_role()`` methods to ``GroupsClient``.

* Added ``full_details`` parameter to ``JobsClient.show_job()`` (thanks to
  Rossano Atzeni).

* BioBlend.objects: added ``ObjJobClient`` and ``Job`` wrapper (thanks to
  Rossano Atzeni).

* BioBlend.objects: added check to verify that all tools in a workflow are
  installed on the Galaxy instance (thanks to
  [Gianmauro Cuccuru](https://github.com/gmauro)).

* Removed several deprecated parameters: see commits [19e168f](https://github.com/galaxyproject/bioblend/commit/19e168f5342f4c791d37694d7039a85f2669df71)
  and [442ae98](https://github.com/galaxyproject/bioblend/commit/442ae98037be7455d57be15542553dc848d99431).

* Verify SSL certificates by default.

* Added documentation about the Tool Shed and properly link all the docs on
  ReadTheDocs.

* Solidified automated testing by using [tox](https://tox.readthedocs.org/) and
  [flake8](https://gitlab.com/pycqa/flake8).

### BioBlend v0.5.3 - 2015-03-18

* Project source moved to new URL - https://github.com/galaxyproject/bioblend

* Huge improvements to automated testing, tests now run against Galaxy
  release 14.02 and all later versions to ensure backward compatibility
  (see `.travis.yml` for details).

* Many documentation improvements (thanks to
  [Helena Rasche](https://github.com/erasche)).

* Added Galaxy clients for the tool data tables, the roles, and library
  folders (thanks to [Anthony Bretaudeau](https://github.com/abretaud)).

* Added method to get the standard error and standard output for the
  job corresponding to a Galaxy dataset (thanks to
  [Anthony Bretaudeau](https://github.com/abretaud)).

* Added ``get_state()`` method to ``JobsClient``.

* Added ``copy_from_dataset()`` method to ``LibraryClient``.

* Added ``create_repository()`` method to ``ToolShedRepositoryClient`` (thanks
  to [Helena Rasche](https://github.com/erasche)).

* Fixed ``DatasetClient.download_dataset()`` for certain proxied Galaxy
  deployments.

* Made ``LibraryClient._get_root_folder_id()`` method safer and faster for
  Galaxy release 13.06 and later.

* Deprecate and ignore invalid ``deleted`` parameter to
  ``WorkflowClient.get_workflows()``.

* CloudMan: added method to fetch instance types.

* CloudMan: updated cluster options to reflect change to SLURM.

* BioBlend.objects: deprecate and ignore invalid ``deleted`` parameter
  to ``ObjWorkflowClient.list()``.

* BioBlend.objects: added ``paste_content()`` method to ``History`` objects.

* BioBlend.objects: added ``copy_from_dataset()`` method and ``root_folder``
  property to ``Library`` objects.

* BioBlend.objects: added ``container`` and ``deleted`` attributes to ``Folder``
  objects.

* BioBlend.objects: the ``parent`` property of a ``Folder`` object is now set to
  its parent folder object (thanks to John M. Eppley).

* BioBlend.objects: added ``deleted`` parameter to ``list()`` method
  of libraries and histories.

* BioBlend.objects: added ``state`` and ``state_details`` attributes to
 ``History`` objects (thanks to [Gianmauro Cuccuru](https://github.com/gmauro)).

* BioBlend.objects: renamed ``upload_dataset()`` method to ``upload_file()``
  for ``History`` objects.

* BioBlend.objects: renamed ``input_ids`` and ``output_ids`` attributes of
  ``Workflow`` objects to ``source_ids`` and ``sink_ids`` respectively.

* Add ``run_bioblend_tests.sh`` script (useful for Continuous Integration
  testing).

### BioBlend v0.5.2 - 2014-10-17

* BioBlend.objects: enabled email&password auth

* Enabled Tool Shed tar ball uploads

* BioBlend.objects: implemented deletion of history and library datasets

* BioBlend.objects: fixed library dataset downloads

* Fixed the Tool Shed tool installation method

* Added 'deleted' attribute to DatasetContainer

* Handle `data_type` changes in the Oct 2014 Galaxy release

* Renamed `get_current_history()` to `get_most_recently_used_history()`

* A number of documentation improvements and other small fixes (see
  the commit messages for more details)

### BioBlend v0.5.1 - 2014-08-19

* Fixed url joining problem described in issue #82

* Enabled Travis Continuous Inetgration testing

* Added script to create a user and get its API key

* Deprecated ``create_user()`` method in favor of clearer
  ``create_remote_user()``. Added ``create_local_user()``.

* Skip instead of fail tests when ``BIOBLEND_GALAXY_URL`` and
  ``BIOBLEND_GALAXY_API_KEY`` environment variables are not defined.

* Added export and download to objects API

* Added export/download history

* GalaxyClient: changed ``make_put_request()`` to return whole ``requests``
  response object

* Added Tool wrapper to *BioBlend.objects* plus methods to list tools and get
  one.

* Added ``show_tool()`` method to ``ToolClient`` class

* Added ``name``, ``in_panel`` and ``trackster`` filters to ``get_tools()``

* Added ``upload_dataset()`` method to ``History`` class.

* Removed ``DataInput`` and ``Tool`` classes for workflow steps. ``Tool`` is to
  be used for running single tools.
