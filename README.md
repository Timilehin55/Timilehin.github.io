<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Virtual Phone Manager</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        primary: '#5D5CDE',
                        'primary-dark': '#4B4BC8'
                    }
                }
            }
        }
    </script>
    <style>
        .phone-card {
            transition: all 0.3s ease;
        }
        .phone-card:hover {
            transform: translateY(-2px);
        }
        .loading {
            animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
        }
        .call-animation {
            animation: ring 1s ease-in-out infinite;
        }
        @keyframes ring {
            0%, 50% { transform: scale(1); }
            25%, 75% { transform: scale(1.05); }
        }
    </style>
</head>
<body class="bg-white dark:bg-gray-900 text-gray-900 dark:text-white min-h-screen">
    <div class="container mx-auto px-4 py-6 max-w-6xl">
        <!-- Header -->
        <div class="mb-8">
            <h1 class="text-3xl font-bold text-center mb-2">Virtual Phone Manager</h1>
            <p class="text-gray-600 dark:text-gray-400 text-center">Manage your virtual phone numbers</p>
        </div>

        <!-- API Status -->
        <div id="apiStatus" class="mb-6 
