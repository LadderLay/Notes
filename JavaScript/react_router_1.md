## primary components
- routers
- route matchers
- navigation/route changers

### routers
<BrowserRouter>
regular url
<HashRouter>
looks like /#/

a router should be rendered at the root of your element hirarchy

### route matchers
<Switch>
<Route>
attention: 
the <Route path> match the **beginning** of the url, not the whole.
 a <Route path="/"> will always match the URL. 

 ### Navigation

 ## Scroll

 ## APIs
 hook:
 ### useHistory
 ```
let history = useHistory();

function handleClick() {
    /...
    history.push("/login)
}
 ```
 ### useLocation
 ### useParams
 