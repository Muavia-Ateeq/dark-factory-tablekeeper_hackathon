# Tablekeeper

Tablekeeper is a restaurant reservation service built for the **tablekeeper** track of
*WeAreDevelopers x BAND: AI Dark Factory*. It includes four progressively developed,
standalone stages, from a reservation API to a browser-based booking service with policies,
reservation history, recurring bookings, and seating changes.

The project was built by three coding-agent seats in Band Desktop from one dispatched task,
with no human steering during the run.

## Features by stage

| Stage | Included functionality |
|---|---|
| [Stage 1](stage-1/) | Reservation API |
| [Stage 2](stage-2/) | Browser booking interface and combined tables |
| [Stage 3](stage-3/) | Policies, reservation history, and recurring reservations |
| [Stage 4](stage-4/) | Seating changes and recurring reservation amendments |

Each stage is a complete, standalone Node.js service. Stages 2–4 include a browser interface;
stage 1 exposes the API only. Data is held in memory and is cleared when the service stops.

## Run the project

You need Node.js 22 or Docker. Choose a stage and run it from that stage's directory. This
example starts stage 4:

```sh
cd stage-4
docker build -t tablekeeper-stage4 .
docker run --rm -p 8080:8080 tablekeeper-stage4
```

Open [http://localhost:8080](http://localhost:8080) to use the browser interface. The health
endpoint is [http://localhost:8080/health](http://localhost:8080/health).

To run without Docker, from the stage directory use Node.js 22 or newer:

```sh
node server.js
```

The service listens on port `8080` by default. Set the `PORT` environment variable to use a
different port. For stage-specific instructions and checks, see that stage's `RUN.md`.

## Repository guide

| Path | Description |
|---|---|
| [`FACTORY.md`](FACTORY.md) | Agent seats, setup, design choices, costs, and failure handling |
| [`mandates/`](mandates/) | Standing instructions for each seat |
| [`TASK.md`](TASK.md) | Task dispatched to the coordinator for the judged run |
| [`room.json`](room.json) | Original Band Desktop room configuration |
| `stage-1/` … `stage-4/` | Standalone service implementations and run guides |

Git history is preserved as created by the coding-agent seats.

## Team

Code Voyagers

## License

MIT, see [`LICENSE`](LICENSE).
