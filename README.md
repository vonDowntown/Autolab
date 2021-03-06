<a href="http://autolabproject.com">
  <img src="http://svgshare.com/i/2Mf.svg" width="380px" height="100px">
</a>

Autolab is a course management service, initially developed by a team of students at Carnegie Mellon University, that enables instructors to offer autograded programming assignments to their students over the Web. The two key ideas in Autolab are *autograding*, that is, programs evaluating other programs, and *scoreboards*.

Autolab also provides other services that instructors expect in a course management system, including gradebooks, rosters, handins/handouts, lab writeups, code annotation, manual grading, late penalties, grace days, cheat checking, meetings, partners, and bulk emails.

Since 2010, Autolab has had a transformative impact on education at CMU. Each semester, it is used by about 5,000 CMU students in courses in Pittsburgh, Silicon Valley, Qatar, and Rwanda. In Fall, 2014, we are releasing Autolab as an open-source system, where it will be available to schools all over the world, and hopefully have the same impact it's had at CMU.


<p>
<a href="https://autolab-slack.herokuapp.com" style="float:left">
  <img src="http://svgshare.com/i/2Rm.svg" width="170px" height="44px">
</a>

<a href="https://autolab.github.io/docs/" style="float:left">
  <img src="https://svgshare.com/i/B4h.svg" width="170px" height="44px">
</a>

</p>

[![Build Status](https://travis-ci.org/autolab/Autolab.svg)](https://travis-ci.org/autolab/Autolab)

## Installation

We released new documentation! Check it out [here](https://autolab.github.io/docs).


## Testing

### Setting up Tests

1. Add a test database in `database.yml`

2. Create and migrate the database.
	```sh
	RAILS_ENV=test bundle exec rake db:create
	RAILS_ENV=test bundle exec rake db:migrate
	```
   Do not forget to use `RAILS_ENV=test bundle exec` in front of every rake/rails command.

3. Create necessary directories.

	```
	mkdir attachments/ tmp/
	```

### Running Tests

After setting up the test environment, simply run spec by:

```sh
bundle exec rake spec
```

## Rails 5 Upgrade
We are currently in the process of migrating Autolab to Rails 5.1 and Ruby
2.6.3. The relevant branch is `rails-5-upgrade`. All discovered UI breakages have been
fixed and preliminary integration testing with Tango has been successful. If
there are any discovered issues, please file an issue.

[Update 2020/02/13]: We are almost done with the upgrade, and the new master soon will be running on Rails 5. 
We will continue to maintain a separate rails-4-master branch, which may still receive bug fixes 
but no new features.

## Contributing

We encourage you to contribute to Autolab! Please check out the
[Contributing to Autolab Guide](https://github.com/autolab/Autolab/blob/master/CONTRIBUTING.md) for guidelines about how to proceed. [Join us!](http://contributors.autolabproject.org)



## License

Autolab is released under the [Apache License 2.0](http://opensource.org/licenses/Apache-2.0).

## Using Autolab

Please feel free to use Autolab at your school/organization. If you run into any problems, you can reach the core developers at `autolab-dev@andrew.cmu.edu` and we would be happy to help. On a case by case basis, we also provide servers for free. (Especially if you are an NGO or small high-school classroom)

## Changelog

### [v2.4.0](https://github.com/autolab/Autolab/releases/tag/v2.4.0) (2020/02/08) Speedgrader - The new code viewer 
- The File Tree shows file hierarchy of student’s submission 
  - Click on a file to open 
  - Click on a folder to expand 
- The Symbol Tree allows you to jump quickly to functions in the student’s code 
  - Click on a function to jump 
- You can easily switch between submissions and files 
  - Up/down arrow keys change file 
  - Right/left arrow keys change submission 
- How to use new annotation system: 
  - Make annotations with grade adjustments 
  - Important: annotations can only be made for non-autograded problems (to preserve the original autograded score of the autograded problem) 
  - Annotations grade changes summarized by the Annotations table on the right 
- New: Score for problem automatically updates after annotation score changes based on the following formula (this no longer has to be done manually on the Gradebook): 

 `score = max_score + ∑(annotation score changes) `
- For example, a way to grade style in a deductive manner would be to set the max score for the Style problem, and make annotations with negative score for style violations and zero score for good style 

UI Enhancements 
- Tables are more standardized 
- Fixed text overflowing issues on Gradebook modals 
- Improved standardization and UI for annotations on PDF submissions 

Others 
- Course assistants are now able to submit assignments early 
