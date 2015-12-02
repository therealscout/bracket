# bracket
--
### Basic Web Template Below
<pre>
package main

import (
	"net/http"

	"github.com/cagnosolutions/web"
)

var mux = web.NewMux()
var tmpl = web.NewTmplCache()

func main() {
	mux.AddRoutes(home)
	http.ListenAndServe(":8080", mux)
}

var home = web.Route{"GET", "/home", func(w http.ResponseWriter, r *http.Request) {
	tmpl.Render(w, r, "home.tmpl", web.Model{})
}}
</pre>
