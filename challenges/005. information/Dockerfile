# Base image
FROM alpine AS build

# Get files
WORKDIR /
RUN wget https://mercury.picoctf.net/static/d1375e383810d8d957c04eef9e345732/cat.jpg


# Base image
FROM ubuntu

# Working Directory
WORKDIR /picoctf

# Copy files
COPY --from=build cat.jpg ./

# Flag style
ARG FLAG_STYLE="%s\n"
ENV FLAG_STYLE=$FLAG_STYLE

# Run solution
COPY solution.sh ./
CMD [ "/picoctf/solution.sh" ]
