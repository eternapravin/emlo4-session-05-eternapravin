docker build -t dogbreed -f ./Dockerfile
docker run -it -v /workspaces/emlo4-session-05-eternapravin/:/workspace/ dogbreed python src/train.py
docker run -it -v /workspaces/emlo4-session-05-eternapravin/:/workspace/ dogbreed python src/evaluate.py
docker run -it -v /workspaces/emlo4-session-05-eternapravin/:/workspace/ dogbreed python src/infer.py