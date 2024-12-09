<!-- <script context="module" lang="ts">
	import { onMount } from 'svelte';
	import * as jwt from 'jsonwebtoken';
	var userId = '';
	onMount(async () => {
		console.log('The component has mounted');
		makeId();
	});
	function makeId() {
		let length = 10;
		let result = '';
		const characters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789';
		const charactersLength = characters.length;
		let counter = 0;
		while (counter < length) {
			result += characters.charAt(Math.floor(Math.random() * charactersLength));
			counter += 1;
		}
		userId = result;
		console.log(userId);
		createUser();
	}
	function createUser() {
		const options = {
			method: 'POST',
			headers: { accept: 'application/json', 'content-type': 'application/json' },
			body: JSON.stringify({ name: 'user', pictureUrl: 'string', profile: 'string', id: userId })
		};
		fetch('https://chat.botpress.cloud/de683d79-77d9-43f2-8022-98157a783bab/users', options)
			.then((res) => res.json())
			.then((res) => {
				console.log(res);
				userId = res.user.id;
				const key = res.key;
				createConversation(key);
			})
			.catch((err) => console.error(err));
	}
	function createConversation(key:string) {
		if (!key) {
			throw new Error('Encryption key is not defined in the environment variables');
		}
		console.log('Signing JWT with key:', key);
		try {
			const xUserKey = jwt.sign({ id: userId }, key, { algorithm: 'HS256' });
			console.log('Generated User Key:', xUserKey);
			const options = {
				method: 'POST',
				headers: {
					accept: 'application/json',
					'x-user-key': xUserKey,
					'content-type': 'application/json'
				},
				body: JSON.stringify({ id: userId.toString() })
			};
			fetch(
				'https://chat.botpress.cloud/de683d79-77d9-43f2-8022-98157a783bab/conversations',
				options
			)
				.then((res) => res.json())
				.then((res) => console.log(res))
				.catch((err) => console.error(err));
		} catch (error) {
			console.error('Error signing token:', error);
		}
	}
</script> -->
