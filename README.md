# CdmMigrator
This migrator is designed to export individual ContentDM collections to a CSV for refining. It then allows batch importing into Hyku/Hyrax via a CSV upload.

## Installation
Add this line to your application's Gemfile:

```ruby
gem 'cdm_migrator'
```

And then execute:
```bash
$ bundle install
```

Or install it yourself as:
```bash
$ gem install cdm_migrator
```

Finally, run:
```bash
$ rails g cdm_migrator:install
```
to insert the yml and add a link to your Hyrax dashboard

## Usage
1. Add your ContentDM url and api port to the cdm_migrator.yml file.
2. Navigate to the *cdm_migrator/collection* url to select your contentdm collection and what type of work you want to export it to and click "choose mappings".
3. Map the ContentDM fields to your Hyrax work and file fields\* and click "generate CSV".
4. Refine the CSV as you see fit.
5. Navigate to the *cdm_migrator/upload* url; choose your multi-value seperator (default is |) and upload your CSV file.
6. Done.

\* cdm_migrator uses the generated Hyrax forms (ex. Hyrax::Forms::GenericWorkForm) in your host application to obtain it's terms for mapping. If you have added terms to your FileSet model extend the Hyrax::Forms::FileSetEditForm with Hyrax::FileSetForm in your host application so that the changes will be detected by the migrator. You can also add a list of fields in the yml file, under "default fields".


## License
The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).
