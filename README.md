# footsbviz: Visualize StatsBomb Data with Ease

Zero-friction helpers to visualize **StatsBomb Open Data** — without manual data engineering.

> ⚠️ Not affiliated with StatsBomb. Please respect the [StatsBomb Open Data license](https://github.com/statsbomb/open-data/blob/master/LICENSE.txt).

[![PyPI version](https://badge.fury.io/py/footsbviz.svg)](https://pypi.org/project/footsbviz/)

## Features

-   **Shot Maps:** Visualize the location of shots for a team or player.
-   **xG Race Charts:** Track the cumulative expected goals (xG) for both teams over the course of a match.
-   **On-Ball Value (OBV) Charts:** Visualize a player's most valuable dribbles and passes based on the OBV metric.
-   **Passing Networks:** Visualize the passing relationships between players on a team.
-   **Heat Maps:** Visualize the areas of the pitch where a team or player is most active.
-   And more!

## Installation

```bash
pip install footsbviz
# or with optional viz extras:
pip install "footsbviz[viz]"
```

## Quickstart

```python
from statsbombpy import sb
import matplotlib.pyplot as plt
import footsbviz as fz

# Get event data for the 2018 World Cup final
events = sb.events(match_id=7589)

# Create a shot map for France
fig, ax = fz.create_shot_map_team(
    events, team_name="France", team_colour="#0053a0",
    pitch_length_x=120, pitch_length_y=80,
    orientation="horizontal", aspect="full",
    x_dimensions=15, y_dimensions=7
)

# Show the plot
plt.show()
```

## Contributing

Contributions are welcome! Please see the [contributing guide](CONTRIBUTING.md) for more information.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Credits

This library draws inspiration from community work on StatsBomb visuals. Certain function ideas and column expectations originated in publicly shared scripts; we re-implemented them in a package-friendly way and added a stable API. See CREDITS.md for attribution.
