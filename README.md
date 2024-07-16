### PikaNetwork API Demo

#### Fetching Profile Data

To fetch a player's profile data, enter the player's IGN in the input field and click "Fetch Profile". The function `fetchProfileData()` sends a GET request to the PikaNetwork API endpoint for player profiles. Upon success, it dynamically updates the `#profileData` section with details such as Discord verification status, clan information (if available), ranks, and friends list.

#### Fetching Friend Profile Data

Clicking on a friend's username in the friend list will trigger `fetchFriendProfile(username)`, which fetches and displays the profile data of the selected friend similarly to `fetchProfileData()`.

#### Fetching Leaderboard Data

To view leaderboards, select a game mode (e.g., Bedwars or Skywars), a stat (e.g., Wins or Kills), and an interval (e.g., Total or Weekly). Click "Fetch Leaderboard" to send a GET request to the corresponding PikaNetwork API endpoint. The function `fetchLeaderboard()` updates `#leaderboardData` with the leaderboard entries based on the selected criteria.

### How It Works

- **Profile Data**: Retrieves detailed information about a player, their clan, ranks, and friends.
- **Friend Profile**: Allows fetching and displaying detailed profile data for any player in the friend list.
- **Leaderboard**: Displays top players based on selected game mode, stat, and interval, fetched from the PikaNetwork API.

### API Endpoints

- **Profile Data Endpoint**: `https://stats.pika-network.net/api/profile/{playerIGN}`
- **Leaderboard Endpoint**:
  - Bedwars: `https://stats.pika-network.net/api/leaderboards?type=bedwars&stat={stat}&interval={interval}&mode=ALL_MODES&offset=0&limit=10`
  - Skywars: `https://stats.pika-network.net/api/profile/{playerIGN}/leaderboard?type=skywars&interval={interval}&mode=ALL_MODES`

### Notes

- Replace `{playerIGN}` with the player's IGN dynamically fetched from user input or stored data.
- The API responses are handled using AJAX requests (`$.ajax`), ensuring data is fetched asynchronously and displayed dynamically on the webpage.

