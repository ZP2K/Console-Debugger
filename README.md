# Console-Debugger
Console Debugger


Example of usage:

BOOL APIENTRY DllMain(HMODULE hModule,DWORD  ul_reason_for_call,LPVOID lpReserved)
{
	switch (ul_reason_for_call)
	{
	case DLL_PROCESS_ATTACH:
		break;
	case DLL_THREAD_ATTACH:
		break;
	case DLL_THREAD_DETACH:
		break;
	case DLL_PROCESS_DETACH:
		break;
	}
	return TRUE;
}

DWORD WINAPI ATTACHED(LPVOID lpParam)
{
#ifdef DEBUG
	DebugConsole::AttachConsole();
	DebugConsole::ConsolePrint("Debugger initiated!\n");
#endif
	return 1;
}
