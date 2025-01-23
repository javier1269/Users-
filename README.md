CREATE TABLE users (
    user_id SERIAL PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    email VARCHAR(255) UNIQUE NOT NULL,
    phone VARCHAR(20) NOT NULL,
    address TEXT NOT NULL,
    role VARCHAR(50) NOT NULL CHECK (role IN ('Victim', 'Admin')),
    password_hash TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

INSERT INTO users (user_id,name, email, phone, address, role, password_hash) 
VALUES (5, 'Rickey Butcher', 'Ricky.Butcher@outlook.com', '678901234', '74 Reeves Corner', 'Victim', 'Factory36!£');

SELECT * FROM users WHERE role = 'Victim';

UPDATE users 
SET name = 'Rachel Scotland' WHERE user_id = 2;

DELETE FROM users WHERE user_id = 2;
