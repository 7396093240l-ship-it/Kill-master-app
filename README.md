app.pyimport streamlit as st

st.title("Skill-Master Pro App")

# యూజర్ ఇన్పుట్
hours = st.slider("ఎన్ని గంటలు నేర్పిస్తున్నారు?", 1, 10, 1)
is_master = st.checkbox("మీరు మాస్టర్ లెవలా?")
quality_bonus = st.checkbox("క్వాలిటీ బోనస్ అప్లై చేయాలా?")

# పేమెంట్ లాజిక్
def calculate_earnings(hours, is_master, quality_bonus):
    base_rate = 100
    earnings = hours * base_rate
    if is_master:
        earnings += (hours * 50)
    if quality_bonus:
        earnings += 50
    return earnings

# రిజల్ట్ చూపించడం
if st.button("మీ ఆదాయాన్ని లెక్కించండి"):
    total = calculate_earnings(hours, is_master, quality_bonus)
    st.success(f"ఈ సెషన్ ద్వారా వచ్చిన మొత్తం ఆదాయం: ₹{total}")

