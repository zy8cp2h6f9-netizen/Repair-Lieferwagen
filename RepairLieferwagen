import streamlit as st
import streamlit.components.v1 as components

# 1. PAGE CONFIG
st.set_page_config(page_title="Der Repair-Lieferwagen", page_icon="🔧", layout="wide")

# 2. INJECT TAILWIND CSS (This enables the animations/hover effects)
st.markdown("""
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        /* Custom Font fixes for Streamlit */
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap');
        html, body, [class*="css"] {
            font-family: 'Inter', sans-serif; 
        }
        /* Hide default Streamlit padding */
        .block-container {
            padding-top: 2rem !important;
            padding-bottom: 5rem !important;
        }
        /* Hide the top Streamlit menu for cleaner look */
        #MainMenu {visibility: hidden;}
        header {visibility: hidden;}
    </style>
""", unsafe_allow_html=True)

# 3. SVG ICONS (Converted to strings for re-use)
ICON_WRENCH = """<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M14.7 6.3a1 1 0 0 0 0 1.4l1.6 1.6a1 1 0 0 0 1.4 0l3.77-3.77a6 6 0 0 1-7.94 7.94l-6.91 6.91a2.12 2.12 0 0 1-3-3l6.91-6.91a6 6 0 0 1 7.94-7.94l-3.76 3.76z"/></svg>"""
ICON_CALENDAR = """<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="4" width="18" height="18" rx="2" ry="2"></rect><line x1="16" y1="2" x2="16" y2="6"></line><line x1="8" y1="2" x2="8" y2="6"></line><line x1="3" y1="10" x2="21" y2="10"></line></svg>"""
ICON_PHONE = """<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"></path></svg>"""
ICON_USERS = """<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"></path><circle cx="9" cy="7" r="4"></circle><path d="M23 21v-2a4 4 0 0 0-3-3.87"></path><path d="M16 3.13a4 4 0 0 1 0 7.75"></path></svg>"""
ICON_MAP = """<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polygon points="1 6 1 22 8 18 16 22 23 18 23 2 16 6 8 2 1 6"></polygon><line x1="8" y1="2" x2="8" y2="18"></line><line x1="16" y1="6" x2="16" y2="22"></line></svg>"""

# 4. NAVIGATION (Sidebar)
with st.sidebar:
    st.markdown(f"""
    <div style="display:flex; align-items:center; gap:10px; margin-bottom: 20px;">
        <div style="background:#005293; padding:8px; border-radius:8px; color:white;">{ICON_WRENCH}</div>
        <h2 style="margin:0; color:#005293;">Repair Van</h2>
    </div>
    """, unsafe_allow_html=True)
    
    selected_page = st.radio(
        "Menü", 
        ["Startseite", "Was wir reparieren", "Fahrplan", "Über Uns", "Kontakt"],
        label_visibility="collapsed"
    )
    
    st.markdown("---")
    st.info("💡 **Tipp:** Nutzen Sie das Menü hier, um durch die Seite zu navigieren.")

# 5. CONTENT RENDERING
# We use st.markdown(html, unsafe_allow_html=True) to render Tailwind HTML

if selected_page == "Startseite":
    st.markdown(f"""
    <div class="space-y-12">
        <div class="relative rounded-2xl shadow-xl overflow-hidden border border-blue-100 group h-[500px] flex items-center justify-center transition-all duration-500 hover:shadow-2xl">
            <div class="absolute inset-0 z-0">
                <img src="https://images.unsplash.com/photo-1469854523086-cc02fe5d8800?q=80&w=2021" 
                     class="w-full h-full object-cover transition-transform duration-[2s] group-hover:scale-105" />
                <div class="absolute inset-0 bg-gradient-to-br from-[#005293]/90 via-[#003366]/80 to-[#005293]/40 mix-blend-multiply"></div>
            </div>
            <div class="relative z-10 p-10 text-center text-white max-w-3xl">
                <h2 class="text-4xl md:text-5xl font-bold mb-6 drop-shadow-lg">Wir bringen Hilfe <br/>in Ihr Dorf.</h2>
                <p class="text-xl mb-10 opacity-95">Kostenlose Reparaturen & technische Unterstützung – <span class="text-[#F2A900] font-bold">von Schülern für Senioren.</span></p>
                <div class="bg-[#F2A900] text-white px-8 py-4 rounded-lg text-xl font-bold shadow-xl inline-flex items-center gap-3 transform transition-all hover:-translate-y-1">
                    {ICON_CALENDAR} Wann kommen wir?
                </div>
            </div>
        </div>

        <div class="grid md:grid-cols-3 gap-8">
             <div class="bg-white p-8 rounded-xl shadow-md border-t-4 border-[#F2A900] hover:shadow-xl hover:-translate-y-2 transition-all duration-300">
                <div class="text-[#005293] mb-4">{ICON_CALENDAR}</div>
                <h3 class="font-bold text-xl mb-2">1. Fahrplan prüfen</h3>
                <p class="text-gray-600">Schauen Sie nach, wann unser Bus in Ihrem Dorf hält.</p>
             </div>
             <div class="bg-white p-8 rounded-xl shadow-md border-t-4 border-[#005293] hover:shadow-xl hover:-translate-y-2 transition-all duration-300">
                <div class="text-[#005293] mb-4">{ICON_MAP}</div>
                <h3 class="font-bold text-xl mb-2">2. Vorbeikommen</h3>
                <p class="text-gray-600">Bringen Sie Ihr defektes Gerät einfach zum Standplatz.</p>
             </div>
             <div class="bg-white p-8 rounded-xl shadow-md border-t-4 border-[#005293] hover:shadow-xl hover:-translate-y-2 transition-all duration-300">
                <div class="text-[#005293] mb-4">{ICON_WRENCH}</div>
                <h3 class="font-bold text-xl mb-2">3. Reparatur</h3>
                <p class="text-gray-600">Wir reparieren kostenlos und freuen uns auf ein Gespräch.</p>
             </div>
        </div>
    </div>
    """, unsafe_allow_html=True)

elif selected_page == "Was wir reparieren":
    st.markdown(f"""
    <div class="space-y-8 animate-in fade-in">
        <div class="relative h-64 rounded-2xl overflow-hidden shadow-lg group">
            <img src="https://images.unsplash.com/photo-1581092921461-eab62e97a780?q=80&w=2070" 
                 class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-700" />
            <div class="absolute inset-0 bg-gradient-to-t from-[#005293] to-transparent opacity-90"></div>
            <div class="absolute bottom-0 left-0 p-8 text-white">
                <h2 class="text-3xl font-bold mb-2">Unsere Services</h2>
                <p class="text-xl opacity-90">Wir reparieren, was wir in der Schule lernen.</p>
            </div>
        </div>

        <div class="grid md:grid-cols-2 gap-6">
            <div class="bg-white p-6 rounded-xl shadow-md border-l-4 border-[#005293] hover:shadow-xl hover:translate-x-2 transition-all duration-300">
                <h3 class="text-xl font-bold mb-2 text-[#005293]">Elektrische Kleingeräte</h3>
                <p class="text-gray-600">Mixer, Toaster, Kaffeemühlen, alte Radios, Lampen.</p>
            </div>
            <div class="bg-white p-6 rounded-xl shadow-md border-l-4 border-[#005293] hover:shadow-xl hover:translate-x-2 transition-all duration-300">
                <h3 class="text-xl font-bold mb-2 text-[#005293]">Mechanische Gegenstände</h3>
                <p class="text-gray-600">Wackelige Stühle, klemmende Schubladen, Spielzeug.</p>
            </div>
            <div class="bg-white p-6 rounded-xl shadow-md border-l-4 border-[#005293] md:col-span-2 hover:shadow-xl hover:translate-x-2 transition-all duration-300">
                <h3 class="text-xl font-bold mb-2 text-[#005293]">Technik-Hilfe</h3>
                <p class="text-gray-600">Fragen zum Handy oder Tablet? Wir erklären es Ihnen in Ruhe.</p>
            </div>
        </div>
        
        <div class="bg-orange-50 border-l-4 border-[#F2A900] p-6 rounded-r-xl">
             <h3 class="font-bold text-[#b45309] flex items-center gap-2">⚠️ Wichtiger Hinweis</h3>
             <p class="text-slate-700 mt-2">Großgeräte (Waschmaschinen etc.) können wir im Bus nicht reparieren. Keine Garantie.</p>
        </div>
    </div>
    """, unsafe_allow_html=True)

elif selected_page == "Fahrplan":
    # HTML Table for better styling
    st.markdown("""
    <div class="bg-white rounded-xl shadow-lg overflow-hidden border border-gray-200">
        <div class="p-6 bg-[#005293] text-white">
            <h2 class="text-2xl font-bold">📅 Der Fahrplan</h2>
        </div>
        <table class="w-full text-left border-collapse">
            <thead>
                <tr class="bg-gray-50 border-b">
                    <th class="p-4 font-bold text-gray-600">Datum</th>
                    <th class="p-4 font-bold text-gray-600">Uhrzeit</th>
                    <th class="p-4 font-bold text-gray-600">Gemeinde</th>
                    <th class="p-4 font-bold text-gray-600">Standort</th>
                </tr>
            </thead>
            <tbody class="text-gray-700">
                <tr class="border-b hover:bg-blue-50 transition-colors">
                    <td class="p-4 font-bold text-[#005293]">Mo, 12. Mai</td>
                    <td class="p-4">09:00 – 12:00</td>
                    <td class="p-4">Eppan</td>
                    <td class="p-4">Rathausplatz</td>
                </tr>
                <tr class="border-b hover:bg-blue-50 transition-colors">
                    <td class="p-4 font-bold text-[#005293]">Mi, 14. Mai</td>
                    <td class="p-4">14:00 – 17:00</td>
                    <td class="p-4">Kaltern</td>
                    <td class="p-4">Marktplatz</td>
                </tr>
                <tr class="border-b hover:bg-blue-50 transition-colors">
                    <td class="p-4 font-bold text-[#005293]">Fr, 16. Mai</td>
                    <td class="p-4">09:00 – 12:00</td>
                    <td class="p-4">Sarnthein</td>
                    <td class="p-4">Kirchplatz</td>
                </tr>
            </tbody>
        </table>
    </div>
    <br>
    """, unsafe_allow_html=True)
    st.button("📥 Plan als PDF herunterladen")

elif selected_page == "Über Uns":
    st.markdown(f"""
    <div class="space-y-8">
         <div class="relative rounded-2xl overflow-hidden shadow-xl group h-[400px]">
            <img src="https://images.unsplash.com/photo-1522202176988-66273c2fd55f?q=80&w=2071" 
                 class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-700" />
            <div class="absolute inset-0 bg-gradient-to-t from-[#005293] to-transparent opacity-90"></div>
            <div class="absolute bottom-0 left-0 p-8 w-full">
                <div class="bg-white/10 backdrop-blur-md border border-white/20 p-6 rounded-xl text-white inline-block">
                     <h3 class="text-2xl font-bold mb-2">Klasse 4Log A</h3>
                     <p>Die Schülerinnen und Schüler der TFO Max Valier.</p>
                </div>
            </div>
         </div>
         
         <div class="grid md:grid-cols-2 gap-6">
            <div class="bg-white p-8 rounded-xl shadow-sm border-l-4 border-[#F2A900]">
                <h3 class="font-bold text-2xl mb-3 text-[#005293]">Die Mission</h3>
                <p class="text-gray-700">Wir bauen Brücken zwischen den Generationen. Lernen findet nicht nur im Klassenzimmer statt.</p>
            </div>
            <div class="bg-white p-8 rounded-xl shadow-sm border-l-4 border-[#005293]">
                <h3 class="font-bold text-2xl mb-3 text-[#005293]">Das Team</h3>
                <p class="text-gray-700">Begleitet von unseren Fachlehrern lösen wir Probleme in der Praxis.</p>
            </div>
         </div>
    </div>
    """, unsafe_allow_html=True)

elif selected_page == "Kontakt":
    st.markdown(f"""
    <div class="grid md:grid-cols-2 gap-6">
        <div class="bg-gradient-to-br from-[#005293] to-[#003366] text-white p-8 rounded-xl shadow-lg relative overflow-hidden group hover:shadow-2xl hover:-translate-y-1 transition-all duration-300">
             <div class="relative z-10 flex flex-col items-center text-center gap-4">
                <div class="bg-white text-[#005293] p-4 rounded-full shadow-lg group-hover:scale-110 transition-transform">
                    {ICON_PHONE}
                </div>
                <h3 class="text-2xl font-bold">Rufen Sie uns an</h3>
                <p class="text-3xl font-bold text-[#F2A900]">+39 0471 123 456</p>
                <p class="opacity-80">Mo–Fr von 08:00 bis 12:00 Uhr</p>
             </div>
        </div>
        
        <div class="space-y-6">
            <div class="bg-white p-6 rounded-xl shadow-md border-l-4 border-[#F2A900] hover:shadow-xl transition-all group">
                <h3 class="font-bold text-xl mb-2 flex items-center gap-3">
                    <span class="bg-blue-50 p-2 rounded-full text-[#005293] group-hover:bg-[#F2A900] group-hover:text-white transition-colors">{ICON_MAP}</span>
                    Unser Standort
                </h3>
                <p class="text-gray-700">TFO Max Valier<br>Sorrentostraße 20<br>39100 Bozen</p>
            </div>
             <div class="bg-white p-6 rounded-xl shadow-md border-l-4 border-[#F2A900] hover:shadow-xl transition-all group">
                <h3 class="font-bold text-xl mb-2 flex items-center gap-3">
                    <span class="bg-blue-50 p-2 rounded-full text-[#005293] group-hover:bg-[#F2A900] group-hover:text-white transition-colors">{ICON_USERS}</span>
                    E-Mail
                </h3>
                <a href="mailto:info@repair-lieferwagen.it" class="text-[#005293] underline text-lg">info@repair-lieferwagen.it</a>
            </div>
        </div>
    </div>
    """, unsafe_allow_html=True)

# Footer
st.markdown("---")
st.markdown("<p style='text-align:center; color:gray;'>Der Repair-Lieferwagen | Ein Schulprojekt der TFO Max Valier</p>", unsafe_allow_html=True)
