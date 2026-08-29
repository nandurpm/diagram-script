# Src

## Purpose

Contains the production implementation of Diagram Script: command handling, domain rules, storage, reports, and local serving as applicable.

## Contents

- `cli.mjs` — Implements Diagram Script's command-line interface and coordinates validation, persistence, report generation, and local serving.
- `language.mjs` — Tokenizes and parses Diagram Script's diagram language into a validated intermediate representation.
- `render-host.mjs` — Hosts generated Diagram Script diagrams locally and serves only the requested report assets.
- `render.mjs` — Generates and serves Diagram Script's demonstration report through a deployment-friendly HTTP host.

## Responsibilities

Production behavior belongs here. Generated reports, user data, and repository documentation should remain outside this folder.

## Important Notes

- This folder is part of **Diagram Script** and should be kept consistent with the commands and architecture documented in the root README.
- Paths and file roles listed above reflect the current repository implementation.

