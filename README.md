import streamlit as st
import networkx as nx
import matplotlib.pyplot as plt

def create_mind_map():
    # Create a graph
    G = nx.DiGraph()

    # Add nodes and edges to the graph
    G.add_node("Pydot")
    G.add_node("How to install it")
    G.add_node("Way 1")
    G.add_node("Way 2")
    G.add_edge("Pydot", "How to install it")
    G.add_edge("How to install it", "Way 1")
    G.add_edge("How to install it", "Way 2")

    # Define layout for the graph
    pos = nx.spring_layout(G, seed=42)

    # Draw the graph
    nx.draw(G, pos, with_labels=True, node_color='skyblue', node_size=2000, font_size=10, font_weight='bold')
    plt.title("Mind Map Example")
    plt.axis('off')

    # Save the plot as an image
    plt.savefig("mind_map.png", format="PNG")

    # Show the plot using Streamlit
    st.image("mind_map.png")

def main():
    st.title("Mind Map with Python and Streamlit")
    st.write("This is a simple example of a mind map using Streamlit.")

    # Generate and display the mind map
    create_mind_map()

if __name__ == "__main__":
    main()

