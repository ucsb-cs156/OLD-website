---
topic: "React: Introduction"
desc: "Helpful tips for working with frontend code in CS156"
category_prefix: "React: "
indent: true
---

This page is not intended to be a full React tutorial, but a brief overview of some of the 
most important things you need to have at your finger tips when working with React code.


# Six Terminal Windows

While this may seem extreme, I suggest having six terminal windows, each with specific roles to play.

| Num | Name | Directory | Purpose |
|-----|------|-----------|---------|
| 1 | Main | root of repo | Running git commands, and running `code .` to open VS Code |
| 2 | Backend | root of repo | Run backend with `mvn spring-boot:run` |
| 3 | Backend tests | root of repo | Run backend tests with `mvn test` <br /> or Test coverage with `mvn test jacoco:report` |
| 4 | Frontend | `javascript` | Run frontend with `npm start` |
| 5 | Frontend Tests | `javascript` | Run front end unit tests `npm test`<br /> jest coverage with `npm run coverage`, <br />Stryker coverage with `npx stryker run`, <br /> or eslint with `npx eslint --fix src` |
| 6 | Storybook | `javascript` | Run storybook with `npm run storybook` |
{:.table .table-sm .table-striped .table-bordered}

We'll refer to these windows throughout the rest of this cheat sheet.


What is a React Component?

* A React Component is portion of a User Interface.
* By convention, it has a name that starts with a capital letter (e.g. `StudentList`, `CourseForm`, `AdminPage`).
* It can be an entire web page, or just a portion of a page.
* It is considered good practice to write *small* components, i.e. to break down a larger user interface, e.g. an entire web page,
  into smaller components that can be developed, tested, documented and maintained separately.

As an example, here is a animated screenshot of the Home Page of [proj-ucsb-courses-search](http://proj-ucsb-courses-search.herokuapp.com/).

![courses-page-components](proj-ucsb-courses-search-home-page-components.gif)

Here are just a few of the components on this page:

* The entire page is a component, [`main/pages/Home/Home.js`](https://github.com/ucsb-cs156-s21/proj-ucsb-courses-search/blob/main/javascript/src/main/pages/Home/Home.js)
* With the page, there are several components, shown with various colors of dotted outlines, including:
  -  The navigation bar: [`main/components/Nav/AppNavbar.js`](https://github.com/ucsb-cs156-s21/proj-ucsb-courses-search/blob/main/javascript/src/main/components/Nav/AppNavbar.js), which is included in `main/App.js`
  -  The authorization part of the navbar: [`main/components/Nav/AuthNav.js`](https://github.com/ucsb-cs156-s21/proj-ucsb-courses-search/blob/main/javascript/src/main/components/Nav/AuthNav.js), which is included in `AppNavbar.js`
  -  The form that is used to select courses:  [`main/components/BasicCourseSearch/BasicCourseSearchForm.js`](https://github.com/ucsb-cs156-s21/proj-ucsb-courses-search/blob/main/javascript/src/main/components/BasicCourseSearch/BasicCourseSearchForm.js), which is included in `main/pages/Home/Home.js`
  -   The table legend:  [`main/components/BasicCourseSearch/TableLegend.js`](https://github.com/ucsb-cs156-s21/proj-ucsb-courses-search/blob/main/javascript/src/main/components/BasicCourseSearch/TableLegend.js), which is included in `main/pages/Home/Home.js`
  -   The course filters:  [`main/components/BasicCourseSearch/CourseFilters.js`](https://github.com/ucsb-cs156-s21/proj-ucsb-courses-search/blob/main/javascript/src/main/components/BasicCourseSearch/CourseFilters.js), which is included in `main/pages/Home/Home.js`
  -  The table of course results:  [`main/components/BasicCourseSearch/BasicCourseTable.js`](https://github.com/ucsb-cs156-s21/proj-ucsb-courses-search/blob/main/javascript/src/main/components/BasicCourseSearch/BasicCourseTable.js), which is included in `main/pages/Home/Home.js`
  -  The footer for the page:  [`main/components/Footer/AppFooter.js`](https://github.com/ucsb-cs156-s21/proj-ucsb-courses-search/blob/main/javascript/src/main/components/Footer/AppFooter.js), which is included in `main/App.js`
 

# Writing a new component
