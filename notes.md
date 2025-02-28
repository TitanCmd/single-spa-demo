# Project Notes

## Background

This project was created as a demonstration of microfrontend architecture using single-spa. The goal was to showcase how different parts of a frontend application can be developed in isolation while still functioning as a cohesive whole.

So to begin, we spoke of micro-frontends and single-spa during our interview, these are a good example of an architectural decision for frontend, where we can develop separate parts of our frontend in isolated ways.

In the request for this code example as supplemental evidence to support the candidacy I am applying for I was asked to apply relevant concepts.

## Implementation Notes

- The examples for microfrontends are intentionally small, distinct parts of the frontend (e.g., navigation, main module) rather than full-featured modules like reporting, dashboard, analytics, etc.
- This approach was chosen to demonstrate the architectural pattern rather than build a complete application.
- Microfrontends can be separated at various isolation points:
  - UI components (navigation/header)
  - Route-based applications
  - Or a combination of both
- Vue is the main frontend framework used across the repo, with Pinia for scalable state management
- Shared UI components and utilities are stored in a utility package

## Future Enhancements

Potential improvements that could be made to this demo:

- Add more microfrontends for different features
- Add shared component libraries
- Add shared utility functions
- Implement shared state management between microfrontends
- Add authentication and authorization
- Implement CI/CD pipelines for each microfrontend
- Add end-to-end testing

## References

- [Single-SPA Documentation](https://single-spa.js.org/)
- [Micro Frontends](https://micro-frontends.org/)
- [Vue.js Documentation](https://vuejs.org/)
