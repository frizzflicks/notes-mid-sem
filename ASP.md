# 🚀 ASP.NET & C# Refresher (Exam-Friendly)

## 🌐 Introducing ASP.NET and the .NET Platform

ASP.NET is a **free web framework** for building websites and apps using **HTML, CSS, and JavaScript** — with C# running on the server.

It has multiple styles (think of them like _flavors of development_):

### 1. Web Forms 🧩 (Old but classic)

* Event-driven, drag-and-drop style.
* Similar to **WinForms** but for the web.
* Rapid UI building with a toolbox full of controls.

👉 _Modern analogy_: Feels like an early version of building with **React components**, but heavier and server-side.

***

### 2. MVC ⚖️ (Separation of concerns)

* **Model–View–Controller** design.
* Cleaner, testable, and developer-friendly.
* Gives you more control over HTML + CSS output.

👉 _Modern analogy_: Think **Express.js + React** separation.

***

### 3. Web Pages with Razor ✍️

* Lightweight way to mix **C# server code** with HTML.
* Great for smaller projects or learning.

👉 _Modern analogy_: Feels a bit like **EJS / Handlebars templates** in Node.

***

## 📡 Web API

* Framework to build **HTTP services** (REST APIs).
* Works with browsers, mobile apps, IoT.
* Perfect for JSON-based communication.

👉 _Modern analogy_: Like **Express.js APIs**.

***

## ⚡ Real-time with SignalR

* Enables **bi-directional, real-time communication**.
* Server can push updates instantly (like chat apps).
* Uses **WebSockets** (or falls back to other methods if needed).

👉 _Modern analogy_: Like **Socket.IO** in Node.

***

## 📱 Mobile Apps & Sites

* **Native apps** → use Web API as a backend (JSON, auth, push).
* **Mobile websites** → use responsive design (Bootstrap, jQuery Mobile, etc).

👉 _Modern analogy_: What we do with **React Native + REST APIs** today.

***

## 🖼️ Single Page Applications (SPA)

* Build apps with heavy client-side interaction.
* Visual Studio SPA template used **Knockout.js** + Web API.

👉 _Modern analogy_: Same idea as **React / Vue / Angular** SPAs.

***

## 🔔 WebHooks

* Lightweight **pub/sub pattern** for event notifications.
* A service sends an HTTP POST when an event happens (e.g. payment, code push, file update).

Examples: GitHub push → Slack notification, Dropbox file update → app reacts.

👉 _Modern analogy_: Exactly what we use today with **Stripe Webhooks, GitHub Actions, Slack integrations**.

***
## .NET Framework (v4)

* The **.NET Framework** is a software development platform by Microsoft that provides tools, libraries, and runtime support for building and running applications.

* Version **4.0** (released in 2010) was a major update that improved performance, scalability, and developer productivity.

* It supports multiple programming languages like **C#, VB.NET, F#**, etc., which all run on the **Common Language Runtime (CLR)**.

### Key Features of .NET Framework 4

* **CLR Improvements**

  * Better memory management and garbage collection.
  * Enhanced parallel programming with **Task Parallel Library (TPL)**.

* **Base Class Library (BCL)**

  * Rich set of APIs for collections, I/O, networking, XML, LINQ, etc.

* **ASP.NET Enhancements**

  * Improved web development support.
  * Added support for **MVC 2** and better AJAX integration.

* **Windows Communication Foundation (WCF)**

  * Simplified configuration.
  * Better support for REST and SOAP web services.

* **Entity Framework 4.0**

  * Simplifies database access with ORM (Object-Relational Mapping).
  * Supports LINQ queries on databases.

***

⚡ **In short:** .NET Framework 4 provided a **stable, mature, and powerful foundation** for building Windows, Web, and enterprise apps before Microsoft later moved towards the **.NET Core** and now the **modern .NET 8/9** ecosystem.

***

## Structure of an ASP.NET Page

An ASP.NET page isn’t just plain HTML—it’s a mix of server-side and client-side elements that together make your web app dynamic.\
The key building blocks are:

* **Directives**

* **Code Declaration Blocks**

* **ASP.NET Controls**

* **Code Render Blocks**

* **Server-side Comments**

* **Server-side Include Directives**

* **Literal Text & HTML Tags**

***

## 🔹 Directives

Directives control how an ASP.NET page is **compiled**.

👉 They start with `<%@` and end with `%>`.\
👉 Usually written at the **top** of the page.

### **Types of Directives**

1. **Page Directive**
   Used to set the page language, enable tracing, debugging, etc.

```html
<%@ Page Language="C#" %>  
<%@ Page Trace="True" %>  
<%@ Page Debug="True" %>  
```

➡️ Equivalent shorthand:

```html
<%@ Language="C#" %>  
```

✨ You can also **combine multiple attributes**:

```html
<%@ Page Debug="True" Trace="True" %>
```

#### Example: Page Trace

```html
<%@ Page Trace="True" %>
<script runat="server">
  Sub Page_Load
    Trace.Warn("Page_Load event executing!") 
    Dim msg As String = "Hello World!"
    Trace.Write("The value of msg is " & msg)
  End Sub
</script>
```

***

2. **Import Directive**
   Brings in namespaces so you don’t need full class names.

```html
<%@ Import Namespace="System.Web.Mail" %>
```

Example (sending email):

```html
<script runat="server">
  Sub Page_Load
    Dim mail As New System.Web.Mail.SmtpMail
    mail.Send("bob@x.com","alice@y.com","Hello","Testing email!")
  End Sub
</script>
```

***

## 🔹 Code Declaration Blocks

Contain **variables, methods, subroutines, and logic**.

✅ Must appear inside:

```html
<script runat="server">
  Sub mySub()
    ' Code here
  End Sub
</script>
```

👉 Old ASP Classic style (`<% Sub ... %>`) doesn’t work here!

You can also load code from an **external file**:

```html
<script runat="server" src="ApplicationLogic.aspx" />
```

***

## 🔹 ASP.NET Controls

These are special **server-side controls** that must be inside a
`<form runat="server">`.

Example:

```html
<form runat="server">
  <asp:Label ID="lblMessage" runat="server" />
  <asp:Button Text="Click Here!" OnClick="Button_Click" runat="server" />
</form>
```

⚠️ Rule: Only **one `<form runat="server">` per page** allowed.

***

## 🔹 Code Render Blocks

Used to **mix code with HTML**.

* **Inline code:**

```html
<% strSomeText = "Hello Again!" %>
```

* **Inline expressions (shorthand for Response.Write):**

```html
<%= strSomeText %>
```

Example:

```html
<script runat="server">
  Dim strSomeText As String
  Sub Page_Load
    strSomeText = "Hello!"
  End Sub
</script>

The value of strSomeText is: <%= strSomeText %>
```

***

## 🔹 Server-side Comments

Invisible in browser (unlike HTML comments).

```html
<%-- This is a hidden server-side comment --%>
```

Example:

```html
<%-- <asp:Label Text="Hidden!" runat="server" /> --%>
```

***

## 🔹 Server-side Include Directives

Bring external files into your page before execution.

* File relative path:

```html
<!-- #include file="includefile.aspx" -->
```

* Virtual path:

```html
<!-- #include virtual="/myDirectory/includefile.aspx" -->
```

👉 But user controls (`.ascx`) are usually better than includes.

***

## 🔹 Literal Text & HTML

Static HTML is also compiled into ASP.NET pages as **LiteralControl** objects.

Example:

```html
<script runat="server">
  Sub Page_Load
    Dim ctrl As LiteralControl
    For Each ctrl In Page.Controls
      ctrl.Text = StrReverse(ctrl.Text)
    Next
  End Sub
</script>

<b>This text is reversed!</b>
```

***

✅ **In summary:**
ASP.NET pages combine **directives, code, controls, and plain HTML** into a single compiled unit, making them powerful for web dev.

***

## **Features of Visual Studio IDE**

An **IDE (Integrated Development Environment)** is a feature-rich application that supports all phases of software development—editing, building, debugging, and deploying apps.

Microsoft **Visual Studio** goes beyond a basic editor: it includes compilers, IntelliSense, debuggers, graphical designers, and productivity tools.

***

### **Key Windows in Visual Studio**

* **Solution Explorer (top right):** Organizes files into _solutions_ and _projects_ for easy navigation.
* **Editor Window (center):** Main area for writing code and designing UIs.
* **Git Changes (bottom right):** Provides built-in support for Git and GitHub version control.

***

### **Editions**

* **Community:** Free for students, open-source, and individuals.
* **Professional:** For small teams; includes more collaboration features.
* **Enterprise:** Full suite for large organizations; advanced testing and architecture tools.
  _(Available on Windows & Mac; Mac version optimized for cross-platform dev.)_

***

### **Popular Productivity Features**

* **Squiggles & Quick Actions:** Wavy underlines show errors or warnings; lightbulb icons suggest fixes.
* **Code Cleanup:** Formats code and applies fixes automatically.
* **Refactoring:** Rename variables, extract methods, reorder parameters.
* **IntelliSense:** Auto-complete, member lists, inline documentation.
* **Search (Ctrl+Q):** Find menus, options, code instantly.
* **Live Share:** Real-time collaborative coding and debugging.
* **Call Hierarchy:** See which methods call/are called by others.
* **CodeLens:** Displays references, commits, and test results inline.
* **Go To Definition / Peek Definition:** Jump or preview type/method definitions.

***

### **Installing Visual Studio**

1. Download and run the installer.
2. Select workloads (e.g., **.NET Desktop Development** for C#/VB apps).
3. Sign in with a Microsoft or organizational account.

***

### **Creating Your First Program**

1. Start Visual Studio → _Create a New Project_.
2. Choose **Console App** template → Name it `HelloWorld`.
3. Select framework (e.g., **.NET 6.0**) → Create.
4. Default program:

   ```csharp
   Console.WriteLine("Hello, World!");
   ```

   Run with **Ctrl+F5**.

**Modify Program:**

```csharp
Console.WriteLine("\nWhat is your name?");
var username = Console.ReadLine();
Console.WriteLine($"\nHello {username}!");
```

***

### **Refactoring & IntelliSense Example**

```csharp
DateTime now = DateTime.Now;
int dayOfYear = now.DayOfYear;

Console.WriteLine("Day of year: " + dayOfYear);
```

* Use refactor → _Inline variable_ to simplify.
* IntelliSense suggests `Now` property from `DateTime` class.

***

### **Debugging**

* **Set Breakpoint (F9):** Stops execution at a line.
* **Start Debugging (F5):** Runs program in debug mode.
* **Watch Variables:** Hover or add to Watch window.
* **Step Through Code:** Execute one line at a time.

***

### **Customization**

* **Change Theme:** Tools → Options → Environment → General → Color Theme (Blue/Light/Dark).
* More personalization: shortcuts, window layouts, extensions.

***

✅ **In short:** Visual Studio = powerful IDE with built-in debugging, version control, collaboration, IntelliSense, and customization, making it a complete software development hub.

***
Perfect exam topic 📚🔥 Let’s break this down into **crisp, exam-ready notes** so you can revise fast but still have depth.

***

## 📘 Visual Studio IDE – Exam Notes

***

## 1. **Components of Visual Studio IDE**

Visual Studio IDE (Integrated Development Environment) provides a complete environment for development.

**Main Components:**

* **Solution Explorer** – Manage projects, files, and references.
* **Editor Window** – Write and edit code / UI design.
* **Toolbox** – Drag & drop controls for GUI development.
* **Properties Window** – Modify control and project properties.
* **Server Explorer** – Manage servers, databases, and cloud services.
* **Output Window** – Shows build, debug, and execution results.
* **Error List Window** – Displays compilation errors, warnings, and messages.
* **Team Explorer / Git Changes** – Source control and collaboration features.

***

## 2. **Features of Visual Studio IDE**

* ✅ **Code Editing & Refactoring** – Intelligent suggestions, quick fixes, and code cleanup.
* ✅ **Code Navigation** – _Go To Definition_, _Peek Definition_, _Call Hierarchy_, _CodeLens_.
* ✅ **Productivity Tools** – Squiggles (error hints), IntelliSense, search (Ctrl+Q), Code Cleanup.
* ✅ **Collaboration** – Live Share for real-time editing and debugging.
* ✅ **Testing & Debugging** – Unit test support, breakpoint management, and step-through debugging.
* ✅ **Multiple Language Support** – C#, VB.NET, C++, Python, JavaScript, etc.
* ✅ **Cross-Platform Development** – Build desktop, mobile, web, and cloud applications.
* ✅ **Customization** – Themes, extensions, layout adjustments.

***

## 3. **Code Editor Features**

### 🔹 IntelliSense

* Provides auto-completion, parameter info, quick info, and member lists.
* Helps reduce syntax errors and speed up coding.
* Example: Typing `DateTime.` shows all available members (Now, Today, etc.).

### 🔹 Browser Link

* Connects Visual Studio with one or more browsers.
* Allows real-time updates in browser when code is changed.
* Useful in **web development** (especially ASP.NET).

### 🔹 Themes

* IDE supports **Dark, Light, Blue**, and custom themes.
* Improves readability and user experience.

### 🔹 Debugger

* One of the most powerful features.
* Provides:

  * Breakpoints
  * Step Into / Step Over / Step Out
  * Watch & Immediate windows
  * Exception handling visualization
* Helps detect runtime errors, logic errors, and performance issues.

***

## 4. **Executing a Project**

### 🔹 Using Built-in Web Server

* Visual Studio provides a **lightweight development server**.
* Example: _IIS Express_ runs automatically when debugging web projects.
* Best for quick local testing.

### 🔹 Using IIS (Internet Information Services)

* Full-fledged **Windows web server**.
* Allows enterprise-level hosting, security, and scalability.
* Best for deployment and production testing.

***

# ✅ Quick Revision Table

| **Topic**        | **Key Points**                                                                      |
| ---------------- | ----------------------------------------------------------------------------------- |
| **Components**   | Solution Explorer, Editor, Toolbox, Properties, Output, Error List, Server Explorer |
| **Features**     | Code navigation, refactoring, collaboration, debugging, multi-language support      |
| **IntelliSense** | Auto-completion, tooltips, quick info                                               |
| **Browser Link** | Real-time updates in browsers                                                       |
| **Themes**       | Dark/Light/Blue/custom themes                                                       |
| **Debugger**     | Breakpoints, step-through, watches                                                  |
| **Execution**    | Built-in web server (IIS Express), IIS for production                               |

***

***

## 🌐 Web Server Controls in ASP.NET

ASP.NET Web Server Controls are **special controls processed on the server**, unlike plain HTML controls. They can **maintain state, raise events, and interact with server-side code**.

***

## 1. **Standard Web Server Controls**

These are basic UI elements that perform standard tasks:

| **Control**                | **Purpose / Use**                        | **Example**                               |
| -------------------------- | ---------------------------------------- | ----------------------------------------- |
| **TextBox**                | Accepts user input.                      | Login forms, search boxes                 |
| **Label**                  | Displays text or messages on the page.   | “Welcome, User!”                          |
| **Button**                 | Triggers server-side events like clicks. | Submit button                             |
| **CheckBox / RadioButton** | Allow selection of options.              | Agree to terms checkbox, gender selection |
| **HyperLink**              | Navigation to other pages or URLs.       | “Go to Homepage” link                     |
| **Image**                  | Displays images from server or URL.      | Product images in e-commerce site         |

**Key Points:**

* Automatically **maintains state** across postbacks (via ViewState).
* Can **raise server-side events**, e.g., a Button triggers a Page_Load or Click event.
* Rendered as HTML in the browser but controlled from server.

***

## 2. **List Controls**

These controls let users select one or more items from a list.

| **Control**         | **Purpose / Use**                            | **Example**                |
| ------------------- | -------------------------------------------- | -------------------------- |
| **DropDownList**    | Single selection from a dropdown menu.       | Country selection          |
| **ListBox**         | Can allow single or multiple selections.     | Selecting favorite courses |
| **CheckBoxList**    | Group of checkboxes for multiple selection.  | Interests selection        |
| **RadioButtonList** | Group of radio buttons for single selection. | Gender selection           |

**Key Points:**

* Can **bind to data sources** like databases or arrays.
* Supports **events like SelectedIndexChanged** to handle user actions.
* Enhances **user interaction** compared to plain HTML lists.

***

### 📝 Quick Tips for Exams:

* Always mention **state management** as a key feature.
* Give **1–2 examples per control**.
* Emphasize that **all server controls generate HTML automatically** for browser rendering.
* Standard controls = basic UI elements, List controls = selection-based UI.

***

## 🔑 Understanding Cache vs Cookie vs Session

At first glance, these three seem similar because they all “store something” for a web app. But they serve **different purposes** and work in **different places**.

***

## 📦 What is Cache, Cookie, and Session?

### **1. Cache**

* Temporary storage used by browsers (and sometimes servers).
* Stores **static resources** like images, CSS, scripts, and previously fetched data.
* Goal → **Speed up page load** by avoiding repeated downloads.
* Stored on **client’s browser**.
* Contains **no personal info** about the user.

***

### **2. Cookie**

* Small text file stored in the browser by a website.
* Stores **user-specific data** like login status, preferences, or browsing behavior.
* Sent to the server with every HTTP request.
* Has an **expiration time** (can be short-lived or persistent).
* **Size limit:** ~4KB.

***

### **3. Session**

* A server-side storage mechanism.
* Holds **user-related temporary data** like shopping cart, authentication status, etc.
* Identified via a **Session ID** (usually stored in a cookie).
* Ends when:

  * User logs out
  * Browser is closed
  * Session expires (timeout).
* **Size:** No strict limit like cookies.

***

## ⚖️ Differences

### **Cache vs Cookie**

* **Cache** → Speeds up website load time (focus on performance).
* **Cookie** → Stores small user info (focus on personalization).
* Cache = images, scripts, data files
* Cookie = login info, preferences

***

### **Cookie vs Session**

* **Cookie** → Stored **on the client/browser**
* **Session** → Stored **on the server**
* Cookie persists until expiry
* Session usually ends with logout/timeout
* Cookie is size-limited (4KB)
* Session has no strict size limit

***

## 🛒 Example: Online Shopping

* **Cache** → Makes product images and pages load quickly when you revisit.
* **Cookie** → Auto-fills your login email or remembers language preference.
* **Session** → Keeps track of the items in your shopping cart until checkout.

***

## 📊 Summary Table

| Feature      | Cache                 | Cookie                       | Session                    |
| ------------ | --------------------- | ---------------------------- | -------------------------- |
| **Location** | Browser               | Browser                      | Server                     |
| **Purpose**  | Faster page loads     | Store user preferences/login | Track live user activity   |
| **Lifespan** | Until cleared/expired | Until expiration time        | Until logout/close/timeout |
| **Capacity** | Large                 | Small (~4KB)                 | Large                      |

***

👉 So, quick memory tip:

* **Cache = Speed** ⚡
* **Cookie = Remember me** 🍪
* **Session = Temporary state** 🛍️

***

# ⚡ Control Events and Page Events in ASP.NET (Subroutines)

ASP.NET Web Forms provide **events** to handle both **page lifecycle stages** and **user interactions with controls**. Developers write **subroutines (event handlers)** to respond to these events.

***

## 📄 Page Events (Lifecycle Subroutines)

ASP.NET pages follow a strict **lifecycle**, with events triggered at each stage:

* **PreInit** → Set themes, master pages, or dynamic controls early.
* **Init** → Controls are initialized (but view state not yet restored).
* **InitComplete** → All controls initialized; view state tracking begins.
* **PreLoad** → Before postback data is restored to controls.
* **Load** → Runs first for page, then child controls. Use for initializing controls / data binding.
* **LoadComplete** → Page loading finishes, control events + validation done.
* **PreRender** → Last chance to update content before rendering.
* **PreRenderComplete** → All controls have completed their PreRender.
* **SaveStateComplete** → ViewState/control state saved.
* **Unload** → Final cleanup (close DB connections, dispose objects).

📌 **Handled in Code-behind** → e.g. `Protected Sub Page_Load(...) Handles Me.Load`

***

## 🎛️ Control Events

ASP.NET **controls** (Button, TextBox, GridView, etc.) have their own events:

1. **User Interaction Events**

   * Examples: `Click` (Button), `TextChanged` (TextBox), `SelectedIndexChanged` (DropDownList).

2. **Lifecycle Events**

   * Controls also raise `Init`, `Load`, `PreRender` in sync with page lifecycle.

3. **Data-Related Events**

   * Data-bound controls: `DataBinding`, `RowCommand`, `ItemCommand`, etc.

***

## 🛠️ Handling Events

* **Page Events**:

  * Auto wired if `AutoEventWireup="true"` in `@Page` directive.
  * Convention: `Page_Load`, `Page_PreRender`, etc.

* **Control Events**:

  1. **Declaratively** (in .aspx):

     ```asp
     <asp:Button ID="btnSubmit" runat="server" OnClick="btnSubmit_Click" />
     ```
  2. **Programmatically** (in code-behind):

     ```csharp
     btnSubmit.Click += new EventHandler(btnSubmit_Click);
     ```

     ```vb
     AddHandler btnSubmit.Click, AddressOf btnSubmit_Click
     ```
  3. **VB.NET Handles Clause**:

     ```vb
     Protected Sub btnSubmit_Click(...) Handles btnSubmit.Click
     ```

***

## 📝 Quick Comparison

| Feature        | Page Events                              | Control Events                               |
| -------------- | ---------------------------------------- | -------------------------------------------- |
| **Scope**      | Entire Page Lifecycle                    | Individual Controls                          |
| **Examples**   | `PreInit`, `Load`, `PreRender`, `Unload` | `Click`, `TextChanged`, `DataBinding`        |
| **Handled in** | Code-behind (Page_EventName)             | Declarative, Programmatic, or Handles clause |
| **Purpose**    | Manage lifecycle + page-wide logic       | Handle user actions + control behavior       |

***

👉 **Tip to remember**:

* **Page Events** = _when page runs_ 🖥️
* **Control Events** = _when user acts_ 👆

***

## Steps in Developing a Web Application (Example: Shopping Cart in ASP.NET Web Forms)

Developing a web application such as a **Shopping Cart** in ASP.NET involves a series of structured steps. These steps ensure that the application is **well-organized, reusable, maintainable, and visually consistent**.

***

## 1. **Requirement Analysis and Design**

* Identify the features: product listing, add to cart, update quantity, checkout, etc.

* Plan navigation and layout (home page, product pages, cart page, checkout page).

* Decide on consistent look and feel using **Master Pages, Themes, and Skins**.

***

## 2. **Creating the Master Page**

* **Master Page** defines a **common template** for the whole application (e.g., header, footer, navigation bar).

* Content pages (e.g., Products.aspx, Cart.aspx) plug their unique content into the placeholders of the master page.

* Ensures consistent **branding and layout** across the site.

***

## 3. **Applying Themes, Skins, and Styles**

* **Themes**: A collection of property settings, images, and CSS styles applied uniformly to controls and pages.\
  Example: A theme called _"ShoppingTheme"_ may define fonts, background colors, and control appearance.

* **Skins**: Part of themes; define default styles for server controls like Button, TextBox, GridView.\
  Example: All buttons can share a common skin, giving a uniform design without repeating styles everywhere.

* **Styles (CSS)**: Handle additional formatting and responsiveness (margins, colors, hover effects).

* Together, these ensure **visual consistency and easy maintenance**.

***

## 4. **Defining Web Forms (Pages)**

* **Product Listing Page**: Shows available products, usually bound to a database.

* **Cart Page**: Displays selected items with options to update quantity or remove products.

* **Checkout Page**: Collects customer details and confirms purchase.

* Each page derives its layout from the **Master Page** and styling from **Themes/Skins**.

***

## 5. **Adding Server Controls**

* Use ASP.NET Web Controls like:

  * **GridView / ListView**: Display products.

  * **Button**: Add to Cart / Checkout.

  * **TextBox**: Enter quantity or customer details.

  * **Label**: Show totals, messages.

* Controls automatically apply **skin settings** defined in the theme.

***

## 6. **Managing State**

* Shopping cart requires state management since HTTP is stateless.

* Use:

  * **Session State**: Store cart items temporarily.

  * **View State**: Maintain control data between postbacks.

  * **Cookies**: Remember user preferences.

***

## 7. **Navigation and Master Page Integration**

* All pages link back to the **Master Page** navigation menu.

* Example: A "Cart" link is always visible in the header for easy access.

* Any layout update (like adding a new menu item) is made **once in the master page** and reflects across all content pages.

***

## 8. **Validation and Security**

* Use ASP.NET **validation controls** (RequiredFieldValidator, RangeValidator) for forms like checkout.

* Secure sensitive data using SSL (HTTPS).

* Implement authentication/authorization if login is required.

***

## 9. **Testing and Deployment**

* Test each page’s functionality: product selection, cart updates, checkout process.

* Verify that themes and master pages render properly across browsers.

* Deploy to IIS or Azure web server for real usage.

***

## Summary (Exam-Friendly)

* **Master Page** → Provides a consistent layout.

* **Themes and Skins** → Provide consistent styling for pages and controls.

* **ASP.NET Controls** → Used to display data and interact with users.

* **Session & ViewState** → Used to maintain shopping cart data.

* **Validation & Security** → Ensure safe transactions.

* **Deployment** → Final step for making the app live.

***


# 📘 C# Programming Basics & OOP Concepts – Exam Notes

***

## 🔹 1. Control Events and Subroutines

* **Event**: An action triggered by the user/system (e.g., button click, key press).

* **Event Handler**: Method that executes when event occurs.

```csharp
// Button Click Example
private void btnSubmit_Click(object sender, EventArgs e)
{
    MessageBox.Show("Submitted!");
}
```

* **Subroutine (Void Method)**: Executes a set of instructions but does not return a value.

```csharp
void ShowMessage()
{
    Console.WriteLine("Hello Student!");
}
```

***

## 🔹 2. Page Events (ASP.NET Lifecycle)

* ASP.NET page has specific **lifecycle events**:

  1. **Page\_Init** → initialization.

  2. **Page\_Load** → executed every time page loads.

  3. **Page\_PreRender** → just before rendering.

  4. **Page\_Unload** → cleanup before closing.

```csharp
protected void Page_Load(object sender, EventArgs e)
{
    if (!IsPostBack)
        Response.Write("Page loaded first time!");
}
```

***

## 🔹 3. Variables and Variable Declaration

* **Syntax**: `datatype variableName = value;`

* **Examples**:

```csharp
int age = 20;
string name = "Taran";
bool isStudent = true;
```

* **Types**:

  * Value Types → int, float, double, bool, char, struct

  * Reference Types → string, arrays, classes, objects

***

## 🔹 4. Arrays

* Collection of same-type elements stored in continuous memory.

```csharp
int[] marks = new int[5] { 90, 85, 70, 88, 92 };
Console.WriteLine(marks[2]); // Output: 70
```

* **Looping through array**:

```csharp
foreach (int m in marks)
    Console.WriteLine(m);
```

***

## 🔹 5. Functions (Methods)

* Block of code that performs a task.

```csharp
int Add(int a, int b)
{
    return a + b;
}
```

* **Function Types**:

  * With/without return type.

  * With/without parameters.

* **Overloading**: Same name, different parameter list.

***

## 🔹 6. Operators

* **Arithmetic** → +, -, \*, /, %

* **Relational** → <, >, <=, >=, ==, !=

* **Logical** → &&, ||, !

* **Assignment** → =, +=, -=, \*=

* **Unary** → ++, --

***

## 🔹 7. Conditional Logic

```csharp
if (age >= 18) 
    Console.WriteLine("Adult");
else 
    Console.WriteLine("Minor");

switch (day)
{
    case 1: Console.WriteLine("Monday"); break;
    default: Console.WriteLine("Other Day"); break;
}
```

***

## 🔹 8. Loops

```csharp
// For Loop
for (int i = 0; i < 5; i++) Console.WriteLine(i);

// While Loop
int x = 0;
while (x < 5) { Console.WriteLine(x); x++; }

// Do-While Loop
int y = 0;
do { Console.WriteLine(y); y++; } while (y < 5);
```

***

# 🎯 Object Oriented Programming Concepts

***

## 🔹 1. Objects and Classes

* **Class**: Blueprint for objects.

* **Object**: Instance of a class.

```csharp
class Student
{
    public string Name;
    public void Display()
    {
        Console.WriteLine("Student: " + Name);
    }
}

Student s = new Student();
s.Name = "Taran";
s.Display();
```

***

## 🔹 2. Properties

* Special methods to access private fields.

```csharp
class Employee
{
    public string Name { get; set; }
    public int Age { get; set; }
}
Employee e = new Employee { Name = "Aman", Age = 25 };
```

***

## 🔹 3. Methods

* Defined inside class → can be instance or static.

```csharp
class MathOps
{
    public static int Square(int n)
    {
        return n * n;
    }
}
Console.WriteLine(MathOps.Square(5));
```

***

## 🔹 4. Constructors

* Special methods with same name as class, auto-called when object created.

```csharp
class Car
{
    public string Model;
    public Car(string m) { Model = m; }
}
Car c = new Car("BMW");
```

***

## 🔹 5. Scope

* **Local Variable**: inside method.

* **Instance Variable**: tied to an object.

* **Static Variable**: shared across objects.

***

## 🔹 6. Events

* Mechanism for notification.

```csharp
public delegate void Notify();
public class Process
{
    public event Notify Completed;
    public void Start()
    {
        Console.WriteLine("Process Started");
        Completed?.Invoke();
    }
}
```

***

## 🔹 7. Inheritance

* Reuse of parent class methods/properties.

```csharp
class Animal
{
    public void Eat() { Console.WriteLine("Eating..."); }
}
class Dog : Animal
{
    public void Bark() { Console.WriteLine("Barking..."); }
}
Dog d = new Dog();
d.Eat(); d.Bark();
```

***

## 🔹 8. Namespaces

* Organize code and avoid name conflicts.

```csharp
namespace MyApp
{
    class Test { }
}
using MyApp;
```

***

## 🔹 9. Code-Behind Files (ASP.NET)

* ASPX (UI) + C# (Logic) separation.

* Example:

  * `Default.aspx` → markup

  * `Default.aspx.cs` → backend logic

```csharp
protected void Button1_Click(object sender, EventArgs e)
{
    Label1.Text = "Hello World!";
}
```

***

# ✅ Exam Tips

* **Focus on examples** → usually short programs are asked.

* **Remember syntax** for events, loops, arrays.

* **OOP core topics** (Inheritance, Properties, Constructors) are guaranteed questions.

* **ASP.NET page events + code-behind** = theory-based Qs.

# 🚀 ASP.NET & C# Quick Refresher (Pre-Exam)

## 🌐 ASP.NET & .NET Overview

* **ASP.NET:** Free web framework; C# runs on server, HTML/CSS/JS on client.

* **Types:**

  * **Web Forms 🧩:** Event-driven, drag-drop, like old React components.
  * **MVC ⚖️:** Model-View-Controller, clean separation, testable.
  * **Razor Pages ✍️:** Lightweight C# + HTML template, like EJS/Handlebars.

* **Web API:** Build REST services; JSON-based.

* **SignalR:** Real-time bi-directional communication (like Socket.IO).

* **SPA:** Single Page Apps; client-heavy interaction (React/Vue style).

* **WebHooks:** Pub/sub notifications for events.

* **.NET Framework 4:** CLR, Base Class Library, ASP.NET enhancements, WCF, Entity Framework 4.0.

***

## 🖥️ ASP.NET Page Structure

| Component                      | Purpose                                                       |
| ------------------------------ | ------------------------------------------------------------- |
| Directives                     | Page compilation settings (`<%@ Page Language="C#" %>`)       |
| Code Declaration Blocks        | Methods, variables, logic inside `<script runat="server">`    |
| ASP.NET Controls               | Server-side UI inside `<form runat="server">`                 |
| Code Render Blocks             | Mix server code with HTML (`<%= variable %>`)                 |
| Server-side Comments           | `<%-- hidden comment --%>`                                    |
| Server-side Include Directives | Include external files (`<!-- #include file="file.aspx" -->`) |
| Literal Text & HTML            | Compiled as LiteralControl objects                            |

***

## 🖱️ Visual Studio IDE – Essentials

* **Key Windows:** Solution Explorer, Editor, Toolbox, Properties, Server Explorer, Output, Error List, Git/Team Explorer.
* **Features:** IntelliSense, refactoring, debugging (breakpoints, watches), live collaboration, multi-language support, themes.
* **Execution:** IIS Express (local dev), IIS (production).

***

## 🌐 ASP.NET Web Server Controls

**Standard Controls:** TextBox, Label, Button, CheckBox, RadioButton, HyperLink, Image.
**List Controls:** DropDownList, ListBox, CheckBoxList, RadioButtonList.

* Maintains **state**, raises **server-side events**, auto-generates HTML.

***

## ⚖️ Cache vs Cookie vs Session

| Feature  | Cache                 | Cookie                  | Session                    |
| -------- | --------------------- | ----------------------- | -------------------------- |
| Location | Browser               | Browser                 | Server                     |
| Purpose  | Speed                 | Store preferences/login | Track user activity        |
| Lifespan | Until cleared/expired | Until expiration        | Until logout/close/timeout |
| Capacity | Large                 | ~4KB                    | Large                      |

***

## 🛠️ Events

* **Page Events:** PreInit → Init → Load → PreRender → Unload (whole page lifecycle).
* **Control Events:** Click, TextChanged, SelectedIndexChanged.

**Handlers:**

```csharp
btn.Click += new EventHandler(btn_Click);
protected void btn_Click(object sender, EventArgs e) { ... }
```

***

## 🛒 Web App Dev Steps (Example: Shopping Cart)

1. Requirement Analysis
2. Master Page → layout template
3. Themes & Skins → consistent styling
4. Pages (Product, Cart, Checkout)
5. Add Controls (GridView, Button, TextBox, Label)
6. State Management (Session, ViewState, Cookies)
7. Navigation integration
8. Validation & Security (Validators, SSL, Auth)
9. Testing & Deployment (IIS/Azure)

***

## 💻 C# Basics

* **Variables:** `int age = 20; string name = "Taran"; bool isStudent = true;`
* **Arrays:** `int[] marks = {90,85,70};`
* **Functions/Methods:**

```csharp
int Add(int a, int b) { return a + b; }
```

* **Operators:** `+ - * / %`, `< > <= >= == !=`, `&& || !`, `= += -=`
* **Loops:** `for`, `while`, `do-while`
* **Conditionals:** `if-else`, `switch`

***

## 🏛️ OOP in C#

* **Class & Object:**

```csharp
class Student { public string Name; }
Student s = new Student(); s.Name = "Taran";
```

* **Properties:** `{ get; set; }`
* **Constructors:** Auto-called methods when object is created
* **Methods:** Instance or static
* **Inheritance:** Reuse parent methods
* **Events & Delegates:** Notification mechanism
* **Namespaces:** Organize code (`namespace MyApp {}`)
* **Code-Behind (ASP.NET):** Separation of UI & logic

***

## ⚡ Exam Tips

* Focus on **short examples** for events, loops, arrays.
* Remember **OOP core topics**: Constructors, Inheritance, Properties.
* **ASP.NET Page Events + Code-behind** = theory Qs.
* **Server controls & state management** = hot topic.

***



