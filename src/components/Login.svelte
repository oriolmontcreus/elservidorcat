<script lang="ts">
    import { Input } from "@components/shadcn/ui/input";

    let email: string = "";
    let password: string = "";

    const handleLogin = () => {
        console.log("Email:", email, "Password:", password);
    };
</script>

<div
    class="bg-white dark:bg-gray-800 rounded shadow-md mx-4 p-0 sm:p-8 w-full max-w-sm sm:max-w-md md:max-w-lg lg:max-w-xl xl:max-w-md 2xl:max-w-4xl"
>
    <h2
        class="text-2xl font-bold mb-6 text-center text-gray-900 dark:text-gray-200"
    >
        Iniciar sessió
    </h2>
    <form on:submit|preventDefault={handleLogin} class="space-y-4">
        <div>
            <label
                for="email"
                class="block text-sm font-medium text-gray-700 dark:text-gray-300"
            >
                Email
            </label>
            <Input
                id="email"
                type="email"
                autocomplete="off"
                bind:value={email}
                class="mt-1 block w-full rounded-md border-gray-300 dark:border-gray-700 shadow-sm focus:border-blue-500 dark:focus:border-blue-400 focus:ring focus:ring-blue-200 focus:ring-opacity-50 dark:focus:ring-opacity-20 transition duration-300"
                required
            />
        </div>
        <div>
            <label
                for="password"
                class="block text-sm font-medium text-gray-700 dark:text-gray-300"
            >
                Contrasenya
            </label>
            <Input
                id="password"
                type="password"
                autocomplete="off"
                bind:value={password}
                class="mt-1 block w-full rounded-md border-gray-300 dark:border-gray-700 shadow-sm focus:border-blue-500 dark:focus:border-blue-400 focus:ring focus:ring-blue-200 focus:ring-opacity-50 dark:focus:ring-opacity-20 transition duration-300"
                required
            />
        </div>
        <button
            type="submit"
            class="w-full py-2 px-4 bg-blue-600 text-white rounded-md hover:bg-blue-700 dark:bg-blue-500 dark:hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-offset-2 dark:focus:ring-offset-gray-900 focus:ring-blue-500 dark:focus:ring-blue-400"
        >
            Acceptar
        </button>
    </form>
</div>