
# 9/18/2022

- ENDING SESH:
    - Stopping at:
        >> That gets the tests back to passing (green). Now let’s do a little more tidying up (refactoring). We said the home page doesn’t need to list items, it only needs the new list input field, so we can remove some lines from lists/templates/home.html, and maybe slightly tweak the h1 to say "Start a new To-Do list":

- Starting Section 7.7 - Another Small Step: A Separate Template for Viewing Lists
>> https://www.obeythetestinggoat.com/book/chapter_working_incrementally.html#_another_small_step_a_separate_template_for_viewing_lists

- ~~Starting ~~section 7.6 - Green? Refactor
>> https://www.obeythetestinggoat.com/book/chapter_working_incrementally.html#_green_refactor

- Installed pytest-timeout and the reasons:
    - If a page doesn't properly exist or not redirected properly, it will loop infinitely and not timeout.
        - Reference commit:
            > 3e6ad3c13d84aa7b3cc637d090710a6b5c09a416
        - It's possible that either Playwright, Pytest, or Django's test tool doesn't know what to do if the redirect doesn't work as intended with how the current test setup is at the moment.

- Started on section 7.4 "Iterating Towards the New Design"
>> https://www.obeythetestinggoat.com/book/chapter_working_incrementally.html#_iterating_towards_the_new_design
# 9/17/2022
- Next sesh: Look at RFER 22
    - Currently, starting a new browser session with Playwright isn't working
        - Update (9/18/2022):
            - This might not be needed as its job is accomplished by new_context()

- Started Section 7.2
>> https://www.obeythetestinggoat.com/book/chapter_working_incrementally.html#_implementing_the_new_design_incrementally_using_tdd

- Added "addopts" to pytest.ini
>> https://docs.pytest.org/en/6.2.x/customize.html
# 9/16/2022



- ENDING SESH
    - Next time:
        - LOOK AT THIS EXAMPLE TO RESOLVE sync_to_async ISSUE:
            >> https://github.com/mxschmitt/python-django-playwright/blob/master/test_login.py

- Currently struggling with troubleshooting:
    > else:
            > if not os.environ.get("DJANGO_ALLOW_ASYNC_UNSAFE"):
            > raise SynchronousOnlyOperation(message)
            >            django.core.exceptions.SynchronousOnlyOperation: You cannot call this from an async context - use a thread or sync_to_async.
    - not sure how and where to implement sync_to_async
    - However, the tests still works as intended. This error might be solvable whenever?
    - Occurance of error:
        - When setUpClass and tearDownClass was implemented with StaticLiveServerTestCase

- Started Section 6.2
>> https://www.obeythetestinggoat.com/book/chapter_explicit_waits_1.html#_aside_upgrading_selenium_and_geckodriver

# 9/15/2022


- Starting Section 6
    >> https://www.obeythetestinggoat.com/book/chapter_explicit_waits_1.html
    
# 9/10/2022
- Failed to setup Docker with Playwright.
    - Docker setup does not work.
    - Issues:
        - Alpine isn't supported by Playwright.
            - This includes the Python image, which is Alpine-based.
    - Alternative Docker images: 
        - Ubuntu
            - Building with scratch with Ubuntu is possible, but it takes forever. It would need to download and install a lot of files.
            - This option is subpar as the waiting time is vast.
        - Official Playwright image
            - It is difficult to figure out how to install pytest and other dependencies within this image.
            - This might be more doable, but extra research time is needed.

- Completed Section 5

# 9/9/2022

- Now starting Section 5.5: The Django ORM and Our First Model
    >> https://www.obeythetestinggoat.com/book/chapter_post_and_database.html#_the_django_orm_and_our_first_model

- Finished Section 5.4 

- Included comment'd Selenium code to use as a reference when following the OtTG book.
    - Formatted the code in a chunky comment as it would be easier to reference. It does make the readability harder, but the objective is to easily find what the book is talking about.

# 9/8/2022

- STOPPING SESH @
    - Section 5.4
    >> https://www.obeythetestinggoat.com/book/chapter_post_and_database.html#_three_strikes_and_refactor

- Started Section 5
    >> https://www.obeythetestinggoat.com/book/chapter_post_and_database.html

- Finished Section 4

- Started Section 4.4, "On Refactoring"
>> https://www.obeythetestinggoat.com/book/chapter_philosophy_and_refactoring.html#_on_refactoring

# 9/6/2022

- Start Section 4, "What Are We Doing with All These Tests? (And, Refactoring)"
> https://www.obeythetestinggoat.com/book/chapter_philosophy_and_refactoring.html


- Finished Section 3, "Testing a Simple Home Page"
    > https://www.obeythetestinggoat.com/book/chapter_unit_test_first_view.html

# 9/4/2022
STOPPING SESH:
> Code—​we use django.http.HttpResponse, as predicted:
lists/views.py
>> https://www.obeythetestinggoat.com/book/chapter_unit_test_first_view.html#_our_first_django_app_and_our_first_unit_test