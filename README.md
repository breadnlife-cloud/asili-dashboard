// src/firebase.js (Mock)
export const auth = {
  currentUser: { email: "admin@asiliafricaexpeditions.com" },
};

export const db = {
  collection: () => ({
    orderBy: () => ({
      onSnapshot: (callback) => {
        // Sample enquiries
        const sample = [
          {
            id: "1",
            name: "John Doe",
            email: "john@example.com",
            phone: "123456789",
            message: "I want to book a safari package.",
            department: "Sales",
            status: "New",
            createdAt: new Date(),
          },
          {
            id: "2",
            name: "Jane Smith",
            email: "jane@example.com",
            phone: "987654321",
            message: "Do you offer family discounts?",
            department: "Marketing",
            status: "In Progress",
            createdAt: new Date(),
          },
        ];
        callback({ docs: sample.map((e) => ({ id: e.id, data: () => e })) });
        return () => {};
      },
    }),
  }),
};


