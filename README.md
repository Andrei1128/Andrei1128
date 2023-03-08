Ciusca
#6568

Maces Andrei — 02.03.2023 18:00
Te-ai apucat sa citesti?
Ciusca — 02.03.2023 18:00
da
Ciusca — 02.03.2023 18:18
cand vrei lucram
Maces Andrei — 02.03.2023 18:35
Da boss
În seara asta
Te sun eu cand e
Ciusca — 02.03.2023 18:35
ok
Maces Andrei
 a început un apel care a durat 2 ore.
 — 02.03.2023 19:59
Maces Andrei — 02.03.2023 21:03
mongoose.connect(dbUrl, {
    useNewUrlParser: true,
    useCreateIndex: true,
    useUnifiedTopology: true,
    useFindAndModify: false
});
const db = mongoose.connection;
db.on("error", console.error.bind(console, "connection error:"));
db.once("open", () => {
    console.log("Database connected");
});
Maces Andrei — 02.03.2023 21:28
mongodb+srv://MacesAndrei:Liderulch1@cluster0.iph5p.mongodb.net/?retryWrites=true&w=majority
Ciusca — 03.03.2023 14:47
Imagine
se accepta?
sa fac asa?
Maces Andrei — 03.03.2023 14:47
Da, arata foarte bine
Plus ca ne ajuta in continuare la ce o sa facem
O sa facem legaturi
Ciusca — 03.03.2023 14:48
ok
Ciusca — 03.03.2023 19:30
https://github.com/Andrei1128/MVC-app
GitHub
GitHub - Andrei1128/MVC-app
Contribute to Andrei1128/MVC-app development by creating an account on GitHub.
GitHub - Andrei1128/MVC-app
am dat push
n are validatori si typurile pe schema sunt toate string ca sa nu mi bat capul la inputuri
Maces Andrei — 03.03.2023 20:08
Da si tu .env aici
Ca nu am baza de date
Ciusca — 03.03.2023 20:08
Nu s acasa
Maces Andrei — 03.03.2023 20:08
Sau defapt, esti acasa?
Aaa ok
Pai atunci suna-ma cand ajungi
Ciusca — 03.03.2023 20:08
nicolaevandrei09
Pw Astronaut234
Maces Andrei — 03.03.2023 20:09
Lasa ca imi arati cand vb
Ciusca — 03.03.2023 20:09
Ok
Ciusca
 a început un apel care a durat 33 de minute.
 — 03.03.2023 20:50
Ciusca — 03.03.2023 21:01
PORT=3000
MONGO_URL=mongodb+srv://nicolaevandrei09:Astronaut234@firstcluster.5kpizsu.mongodb.net/?retryWrites=true&w=majority
Maces Andrei — 03.03.2023 21:06
172.23.176.1
Maces Andrei — 03.03.2023 21:21
https://mongoosejs.com/docs/populate.html
Maces Andrei
 a început un apel care a durat 4 minute.
 — 06.03.2023 14:52
Ciusca — 06.03.2023 15:02
https://github.com/Andrei1128/Aplicatie-MVC
GitHub
GitHub - Andrei1128/Aplicatie-MVC
Contribute to Andrei1128/Aplicatie-MVC development by creating an account on GitHub.
GitHub - Andrei1128/Aplicatie-MVC
Maces Andrei — 06.03.2023 15:44
Tema pentru acasa: Trebuie in primul rand sa dai deploy la aplicatie
Dupa ii arati lui Panait absolut tot ce am facut pana acum
Dupa faci o aplicatie alegi tu de care care sa aibe doua crud-uri legate
Timp limita maxim: Joi
Ciusca — 06.03.2023 20:30
ai treaba?
Maces Andrei — 06.03.2023 20:49
Dap
Ciusca — 06.03.2023 20:49
ok
Ciusca — azi la 8:07
https://github.com/Andrei1128/Aplicatie-MVC_v2
GitHub
Andrei1128/Aplicatie-MVC_v2
Contribute to Andrei1128/Aplicatie-MVC_v2 development by creating an account on GitHub.
Andrei1128/Aplicatie-MVC_v2
Maces Andrei — azi la 8:12
mongo firstcluster.5kpizsu.mongodb.net -u nicolaevandrei09 -p Astronaut234
Ciusca — azi la 9:30
from matplotlib import cbook
from matplotlib import cm
from matplotlib.colors import LightSource
import matplotlib.pyplot as plt
import numpy as np

# Load and format data
dem = cbook.get_sample_data('jacksboro_fault_dem.npz', npload=True)
z = dem['elevation']
nrows, ncols = z.shape
x = np.linspace(dem['xmin'], dem['xmax'], ncols)
y = np.linspace(dem['ymin'], dem['ymax'], nrows)
x, y = np.meshgrid(x, y)

region = np.s[5:50, 5:50]
x, y, z = x[region], y[region], z[region]

# Set up plot
fig, ax = plt.subplots(subplot_kw=dict(projection='3d'))

ls = LightSource(270, 45)
# To use a custom hillshading mode, override the built-in shading and pass
# in the rgb colors of the shaded surface calculated from "shade".
rgb = ls.shade(z, cmap=cm.gist_earth, vert_exag=0.1, blend_mode='soft')
surf = ax.plot_surface(x, y, z, rstride=1, cstride=1, facecolors=rgb,
                       linewidth=0, antialiased=False, shade=False)

for angle in range(0, 360*4 + 1):
    # Normalize the angle to the range [-180, 180] for display
    angle_norm = (angle + 180) % 360 - 180

    # Cycle through a full rotation of elevation, then azimuth, roll, and all
    elev = azim = roll = 0
    elev = angle_norm
    azim = angle_norm
    roll = angle_norm

    # Update the axis view and title
    ax.view_init(elev, azim, roll)
    plt.title('Elevation: %d°, Azimuth: %d°, Roll: %d°' % (elev, azim, roll))

    plt.draw()
    plt.pause(.002)
Ciusca — azi la 9:39
import matplotlib.pyplot as plt
import numpy as np


def midpoints(x):
    sl = ()
    for _ in range(x.ndim):
        x = (x[sl + np.index_exp[:-1]] + x[sl + np.index_exp[1:]]) / 2.0
        sl += np.index_exp[:]
    return x


# prepare some coordinates, and attach rgb values to each
r, g, b = np.indices((17, 17, 17)) / 16.0
rc = midpoints(r)
gc = midpoints(g)
bc = midpoints(b)

# define a sphere about [0.5, 0.5, 0.5]
sphere = (rc - 0.5)2 + (gc - 0.5)2 + (bc - 0.5)2 < 0.52

# combine the color components
colors = np.zeros(sphere.shape + (3,))
colors[..., 0] = rc
colors[..., 1] = gc
colors[..., 2] = bc

# and plot everything

ax = plt.figure().add_subplot(projection='3d')
ax.voxels(r, g, b, sphere,
          facecolors=colors,
          edgecolors=np.clip(2colors - 0.5, 0, 1),  # brighter
          linewidth=0.5)
ax.set(xlabel='r', ylabel='g', zlabel='b')
ax.set_axis_off()
ax.set_aspect('equal')

for angle in range(0, 3604 + 1):
    # Normalize the angle to the range [-180, 180] for display
    angle_norm = (angle + 180) % 360 - 180

    # Cycle through a full rotation of elevation, then azimuth, roll, and all
    elev = azim = roll = 0
    elev = angle_norm
    azim = angle_norm
    roll = angle_norm

    # Update the axis view and title
    ax.view_init(elev, azim, roll)
    plt.title('Elevation: %d°, Azimuth: %d°, Roll: %d°' % (elev, azim, roll))

    plt.draw()
    plt.pause(.001)
import matplotlib.pyplot as plt
import numpy as np


def midpoints(x):
    sl = ()
Extinde
matplot3d.py
2 KB
Maces Andrei — azi la 10:02
### Hi there 👋

My name is Andrei and I am a junior software developer.

## 🙋‍♂️ Connect with me
Extinde
message.txt
5 KB
﻿
Maces Andrei#5024
### Hi there 👋

My name is Andrei and I am a junior software developer.

## 🙋‍♂️ Connect with me

<!-- Badges template - https://github.com/badges/shields -->
<p align="center">
    <a href="https://www.linkedin.com/in/maces-andrei-6220011b3/">
        <img alt="Linkedin"
             src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"></a>
</p>
📊 Github stats
<p>
    <a align="center" href="https://github-readme-stats.vercel.app/api?username=RiceaRaul&show_icons=true&count_private=true&theme=react&hide_border=true&bg_color=1F222E&title_color=F85D7F&icon_color=F8D866"><img alt="Andrei Maces Stats"
                    src="https://github-readme-stats.vercel.app/api?username=AndreiMaces&show_icons=true&count_private=true&theme=react&hide_border=true&bg_color=1F222E&title_color=F85D7F&icon_color=F8D866" /></a>
  <a align="center" href="https://github-readme-stats.vercel.app/api/top-langs/?username=AndreiMaces&langs_count=8&layout=compact&theme=react&hide_border=true&bg_color=1F222E&title_color=F85D7F&icon_color=F8D866">
    <img alt="AndreiMaces's Top Languages" src="https://github-readme-stats.vercel.app/api/top-langs/?username=AndreiMaces&langs_count=8&layout=compact&theme=react&hide_border=true&bg_color=1F222E&title_color=F85D7F&icon_color=F8D866" /></a>
</p>

<p>
  <a align="center" href="#">
    <img src="https://github-profile-trophy.vercel.app/?username=AndreiMaces&theme=monokai&column=8&no-frame=true&no-bg=true">
  </a>
</p>

## 🛠️ My favorite tools

### Programming Languages
<p>
    <a href="#">
        <img alt="JavaScript"
             src="https://img.shields.io/badge/JavaScript-323330?style=for-the-badge&logo=javascript&logoColor=F7DF1E" />
	</a>
    <a href="#">
        <img alt="Python"
             src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
	</a>
    <a href="#">
        <img alt="C"
             src="https://img.shields.io/badge/c-%2300599C.svg?style=for-the-badge&logo=c&logoColor=white" />
	</a>
    <a href="#">
        <img alt="C++"
             src="https://img.shields.io/badge/c++-%2300599C.svg?style=for-the-badge&logo=c%2B%2B&logoColor=white" />
	</a>
    <a href="#">
        <img alt="SQL"
             src="https://img.shields.io/badge/SQL%20-%23025E8C.svg?style=for-the-badge&logo=amazon-dynamodb&logoColor=white" />
	</a>
    <a href="#">
        <img alt="C#"
             src="https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=c-sharp&logoColor=white" />
	</a>
    <a href="#">
        <img alt="PHP"
             src="https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white" />
	</a>
</p>


### Tools

<p>
    <a href="#">
        <img alt="NodeJS"
             src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white"></a>
    <a href="#">
        <img alt="NPM"
             src="https://img.shields.io/badge/npm-CB3837?style=for-the-badge&logo=npm&logoColor=white"/></a>
    <a href="#">
        <img alt="Express.JS"
             src="https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white"/>
	</a>
    <a href="#">
        <img alt="Bootstrap 5"
             src="https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white"/>
	</a>
     <a href="#">
        <img alt="React"
             src="https://img.shields.io/badge/React-FFFFFF?style=for-the-badge&logo=react&logoColor=6DBFB"/>
	</a>
    <a href="#">
        <img alt="Angular"
             src="https://img.shields.io/badge/Angular-b3b3b3?style=for-the-badge&logo=angular&logoColor=dd1b16"/>
	</a>
</p>

### Databases

<p>
    <a href="#">
        <img alt="MySQL"
             src="https://img.shields.io/badge/MySQL-00000F?style=for-the-badge&logo=mysql&logoColor=white"/>
	</a>
  <a href="#">
        <img alt="MongoDB"
             src="https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white"/></a>
</p>

## My stats

<!-- GitHub Readme Streak Stats - https://github.com/karimcambridge/github-readme-streak-stats -->
<p align="center">
  <a href="#">
    <img title="🔥 Streak stats" alt="AndreiMaces's streak" src="https://github-readme-streak-stats.herokuapp.com/?user=AndreiMaces&theme=monokai-metallian&hide_border=true"/>
  </a>
</p>
message.txt
5 KB
