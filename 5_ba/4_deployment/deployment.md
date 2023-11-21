# FRONTEND/ BACKEND DEPLOYMENT

### Im Backend in der index.js folgendes ergänzen:

```javascript
import path from "path";
import { fileURLToPath } from "url";
const __filename = fileURLToPath(import.meta.url);
const __dirname = path.dirname(__filename);
app.use("/", express.static(path.join(__dirname, "/build")));
app.get("/*", (req, res) => res.sendFile(__dirname + "/build/index.html")); => WICHTIG: diese Zeile unter den routes (z.b.  app.use("/users", usersRouter) schreiben
``` 
Das build Verzeichnis wird erstellt nachdem ihr den Befehl npm run build im Frontend ausgeführt habt.
:exclamation:Achtung bei vite nennt sich das neu erstellte Verzeichnis dist anstelle von build:exclamation:

### Im Frontend

im Frontend noch beim fetch die Route ändern (kein localhost, sondern nur noch z.b. /api/employee
danach npm run build ausführen
und den erstellten neuen Ordner mit dem gebuildeten Projekt (build/ dist) ins backend Projekt verschieben
wenn alles in einem Projekt deployed wird müssen wir nicht auf cors achten