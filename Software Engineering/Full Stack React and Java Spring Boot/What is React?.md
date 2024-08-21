
![[react-icon.png | 100x100 ]]


- React is a library for building modern single-page applications
- Component-based framework
- Declarative views
- Component logic is written with JavaScript
- Supports responsive web design and modern frameworks
	- Bootstrap, Google Material Design and others ...

## Traditional Applications

- Each user action results in a full HTML page load

## Single Page Application

- A web application that is composed of a single page
- Based on user action, the application page is updated
- Normally performs a partial update ... instead of full page load

## `Client Side` ---> `Server`


## Who's using React?

- Dropbox
- WhatsApp
- Facebook

## Key Terms

| TERM          | DEFINITION                                                                                                                                                      |
| ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Component** | Main player in a React application. Has two parts:<br>1. View for user interface<br>2. JavaScript that contains application logic / event handling for the view |
| **Props**     | How we will pass data from a parent component to a child component.                                                                                             |
| **State**     | Contains data about the component.<br>When the state changes, the component will re-render                                                                      |
| **Hooks**     | A way to use local state and other React features without writing a new class                                                                                   |
| **Module**    | A collection of related components, that create a specific view                                                                                                 |

## Creating a React project

- React provides a command-line tool to generate a project
- Generates the starter files to help you bootstrap your project

```node
npx create-react-app my-app
```

## Running your new React project

```node
cd my-app
npm start
```

## Changing the Server Port

```node
set PORT=5100 && npm start
```

## Development Process

```md
1. Get links for remote Bootstrap files
	1. Vist Bootstrap website: www.getbootstrap.com
	2. Add links in index.html
	3. Apply CSS in Component HTML template
		
2. Add links to index.html
3. Apply Bootstrap CSS styles in component HTML template
4. Apply Bootstrap CSS styles in component HTML table
```

