---
title: WPF での Win32 コンテンツのホスト
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: 390f63fca912de6de2a1349363e239eb603df549
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64750616"
---
# <a name="hosting-win32-content-in-wpf"></a><span data-ttu-id="cb401-102">WPF での Win32 コンテンツのホスト</span><span class="sxs-lookup"><span data-stu-id="cb401-102">Hosting Win32 Content in WPF</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cb401-103">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cb401-103">Prerequisites</span></span>

<span data-ttu-id="cb401-104">参照してください[WPF と Win32 の相互運用性](wpf-and-win32-interoperation.md)します。</span><span class="sxs-lookup"><span data-stu-id="cb401-104">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a><span data-ttu-id="cb401-105">Windows Presentation Framework (HwndHost) 内で Win32 のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="cb401-105">A Walkthrough of Win32 Inside Windows Presentation Framework (HwndHost)</span></span>

<span data-ttu-id="cb401-106">再利用する[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]内のコンテンツ[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーションに、 <xref:System.Windows.Interop.HwndHost>、Hwnd のようになりますが、コントロールは[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]コンテンツ。</span><span class="sxs-lookup"><span data-stu-id="cb401-106">To reuse [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] content inside [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications, use <xref:System.Windows.Interop.HwndHost>, which is a control that makes HWNDs look like [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="cb401-107">ような<xref:System.Windows.Interop.HwndSource>、<xref:System.Windows.Interop.HwndHost>が簡単に使用する: から派生<xref:System.Windows.Interop.HwndHost>実装と`BuildWindowCore`と`DestroyWindowCore`メソッドのインスタンスを作成し、<xref:System.Windows.Interop.HwndHost>クラスを派生し、その内部に配置、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="cb401-107">Like <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> is straightforward to use: derive from <xref:System.Windows.Interop.HwndHost> and implement `BuildWindowCore` and `DestroyWindowCore` methods, then instantiate your <xref:System.Windows.Interop.HwndHost> derived class and place it inside your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>

<span data-ttu-id="cb401-108">場合、[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]ロジックがすでにをコントロールとしてパッケージ化された、`BuildWindowCore`実装はへの呼び出しよりも少し`CreateWindow`します。</span><span class="sxs-lookup"><span data-stu-id="cb401-108">If your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] logic is already packaged as a control, then your `BuildWindowCore` implementation is little more than a call to `CreateWindow`.</span></span> <span data-ttu-id="cb401-109">たとえば、作成するため、[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]の LISTBOX コントロール[!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="cb401-109">For example, to create a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] LISTBOX control in [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]:</span></span>

```cpp
virtual HandleRef BuildWindowCore(HandleRef hwndParent) override {
    HWND handle = CreateWindowEx(0, L"LISTBOX",
    L"this is a Win32 listbox",
    WS_CHILD | WS_VISIBLE | LBS_NOTIFY
    | WS_VSCROLL | WS_BORDER,
    0, 0, // x, y
    30, 70, // height, width
    (HWND) hwndParent.Handle.ToPointer(), // parent hwnd
    0, // hmenu
    0, // hinstance
    0); // lparam

    return HandleRef(this, IntPtr(handle));
}

virtual void DestroyWindowCore(HandleRef hwnd) override {
    // HwndHost will dispose the hwnd for us
}
```

<span data-ttu-id="cb401-110">しかし、[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]コードでは自己完結型ではそれほど大きくありませんか?</span><span class="sxs-lookup"><span data-stu-id="cb401-110">But suppose the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] code is not quite so self-contained?</span></span> <span data-ttu-id="cb401-111">そのため、作成できる場合、 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]  ダイアログ ボックスしより大きなにそのコンテンツを埋め込む[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="cb401-111">If so, you can create a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog box and embed its contents into a larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="cb401-112">これでサンプルを示します[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]と[!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]が、これは別の言語でまたはコマンドラインで実行することも、します。</span><span class="sxs-lookup"><span data-stu-id="cb401-112">The sample shows this in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] and [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)], although it is also possible to do this in a different language or at the command line.</span></span>

<span data-ttu-id="cb401-113">単純なダイアログ ボックスがコンパイルを開始、 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="cb401-113">Start with a simple dialog, which is compiled into a [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] project.</span></span>

<span data-ttu-id="cb401-114">次に、大きい方に、ダイアログの導入[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="cb401-114">Next, introduce the dialog into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application:</span></span>

- <span data-ttu-id="cb401-115">コンパイル、[!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]管理対象として (`/clr`)</span><span class="sxs-lookup"><span data-stu-id="cb401-115">Compile the [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] as managed (`/clr`)</span></span>

- <span data-ttu-id="cb401-116">コントロールに、ダイアログ ボックスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="cb401-116">Turn the dialog into a control</span></span>

- <span data-ttu-id="cb401-117">派生クラスを定義<xref:System.Windows.Interop.HwndHost>で`BuildWindowCore`と`DestroyWindowCore`メソッド</span><span class="sxs-lookup"><span data-stu-id="cb401-117">Define the derived class of <xref:System.Windows.Interop.HwndHost> with `BuildWindowCore` and `DestroyWindowCore` methods</span></span>

- <span data-ttu-id="cb401-118">オーバーライド`TranslateAccelerator`ダイアログ キーを処理するメソッド</span><span class="sxs-lookup"><span data-stu-id="cb401-118">Override `TranslateAccelerator` method to handle dialog keys</span></span>

- <span data-ttu-id="cb401-119">オーバーライド`TabInto`をタブ移動をサポートします。</span><span class="sxs-lookup"><span data-stu-id="cb401-119">Override `TabInto` method to support tabbing</span></span>

- <span data-ttu-id="cb401-120">オーバーライド`OnMnemonic`ニーモニックをサポートするためにメソッド</span><span class="sxs-lookup"><span data-stu-id="cb401-120">Override `OnMnemonic` method to support mnemonics</span></span>

- <span data-ttu-id="cb401-121">インスタンスを作成、<xref:System.Windows.Interop.HwndHost>サブクラス化し、右下に置いてから[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]要素</span><span class="sxs-lookup"><span data-stu-id="cb401-121">Instantiate the <xref:System.Windows.Interop.HwndHost> subclass and put it under the right [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element</span></span>

### <a name="turn-the-dialog-into-a-control"></a><span data-ttu-id="cb401-122">コントロールに、ダイアログ ボックスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="cb401-122">Turn the Dialog into a Control</span></span>

<span data-ttu-id="cb401-123">WS_CHILD と DS_CONTROL スタイルを使用して HWND を子にダイアログ ボックスを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cb401-123">You can turn a dialog box into a child HWND using the WS_CHILD and DS_CONTROL styles.</span></span> <span data-ttu-id="cb401-124">ダイアログ ボックスが定義されているリソース ファイル (.rc) に移動し、ダイアログ ボックスの定義の先頭を見つけます。</span><span class="sxs-lookup"><span data-stu-id="cb401-124">Go into the resource file (.rc) where the dialog is defined, and find the beginning of the definition of the dialog:</span></span>

```
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU
```

<span data-ttu-id="cb401-125">2 行目を変更します。</span><span class="sxs-lookup"><span data-stu-id="cb401-125">Change the second line to:</span></span>

```
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL
```

<span data-ttu-id="cb401-126">このアクションはいない完全にパッケージ化する自己完結型のコントロールです。呼び出す必要がある`IsDialogMessage()`ように[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]、特定のメッセージを処理することができますが、コントロールの変更はもう 1 つの HWND 内のそれらのコントロールを配置することの簡単な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="cb401-126">This action does not fully package it into a self-contained control; you still need to call `IsDialogMessage()` so [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] can process certain messages, but the control change does provide a straightforward way of putting those controls inside another HWND.</span></span>

## <a name="subclass-hwndhost"></a><span data-ttu-id="cb401-127">サブクラス HwndHost</span><span class="sxs-lookup"><span data-stu-id="cb401-127">Subclass HwndHost</span></span>

<span data-ttu-id="cb401-128">次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="cb401-128">Import the following namespaces:</span></span>

```cpp
namespace ManagedCpp
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Input;
    using namespace System::Windows::Media;
    using namespace System::Runtime::InteropServices;
```

<span data-ttu-id="cb401-129">派生クラスを作成し、<xref:System.Windows.Interop.HwndHost>をオーバーライドし、`BuildWindowCore`と`DestroyWindowCore`メソッド。</span><span class="sxs-lookup"><span data-stu-id="cb401-129">Then create a derived class of <xref:System.Windows.Interop.HwndHost> and override the `BuildWindowCore` and `DestroyWindowCore` methods:</span></span>

```cpp
public ref class MyHwndHost : public HwndHost, IKeyboardInputSink {
    private:
        HWND dialog;

    protected:
        virtual HandleRef BuildWindowCore(HandleRef hwndParent) override {
            InitializeGlobals();
            dialog = CreateDialog(hInstance,
                MAKEINTRESOURCE(IDD_DIALOG1),
                (HWND) hwndParent.Handle.ToPointer(),
                (DLGPROC) About);
            return HandleRef(this, IntPtr(dialog));
        }

        virtual void DestroyWindowCore(HandleRef hwnd) override {
            // hwnd will be disposed for us
        }
```

<span data-ttu-id="cb401-130">ここで使用して、`CreateDialog`コントロールは、実際にダイアログ ボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="cb401-130">Here you use the `CreateDialog` to create the dialog box that is really a control.</span></span> <span data-ttu-id="cb401-131">これは内部で呼び出される最初のメソッドのいずれかであるため、 [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]、いくつかの標準を実行することも必要があります[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]後で、定義する関数を呼び出すことによって初期化と呼ばれる`InitializeGlobals()`:。</span><span class="sxs-lookup"><span data-stu-id="cb401-131">Since this is one of the first methods called inside the [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], you should also do some standard [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] initialization by calling a function you will define later, called `InitializeGlobals()`:</span></span>

```cpp
bool initialized = false;
    void InitializeGlobals() {
        if (initialized) return;
        initialized = true;

        // TODO: Place code here.
        MSG msg;
        HACCEL hAccelTable;

        // Initialize global strings
        LoadString(hInstance, IDS_APP_TITLE, szTitle, MAX_LOADSTRING);
        LoadString(hInstance, IDC_TYPICALWIN32DIALOG, szWindowClass, MAX_LOADSTRING);
        MyRegisterClass(hInstance);
```

### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a><span data-ttu-id="cb401-132">ダイアログ キーを処理するために TranslateAccelerator メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="cb401-132">Override TranslateAccelerator Method to Handle Dialog Keys</span></span>

<span data-ttu-id="cb401-133">このサンプルを実行した場合が表示されたら、ダイアログ コントロールがすべて無視処理は、キーボードの機能 ダイアログ ボックスのダイアログ。</span><span class="sxs-lookup"><span data-stu-id="cb401-133">If you ran this sample now, you would get a dialog control that displays, but it would ignore all of the keyboard processing that makes a dialog box a functional dialog box.</span></span> <span data-ttu-id="cb401-134">今すぐをオーバーライドする必要があります、`TranslateAccelerator`実装 (に由来する`IKeyboardInputSink`、インターフェイスを<xref:System.Windows.Interop.HwndHost>実装)。</span><span class="sxs-lookup"><span data-stu-id="cb401-134">You should now override the `TranslateAccelerator` implementation (which comes from `IKeyboardInputSink`, an interface that <xref:System.Windows.Interop.HwndHost> implements).</span></span> <span data-ttu-id="cb401-135">アプリケーションは、WM_KEYDOWN および WM_SYSKEYDOWN が受信すると、このメソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cb401-135">This method gets called when the application receives WM_KEYDOWN and WM_SYSKEYDOWN.</span></span>

```cpp
#undef TranslateAccelerator
        virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,
            ModifierKeys modifiers) override
        {
            ::MSG m = ConvertMessage(msg);

            // Win32's IsDialogMessage() will handle most of our tabbing, but doesn't know
            // what to do when it reaches the last tab stop
            if (m.message == WM_KEYDOWN && m.wParam == VK_TAB) {
                HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);
                HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);
                TraversalRequest^ request = nullptr;

                if (GetKeyState(VK_SHIFT) && GetFocus() == firstTabStop) {
                    // this code should work, but there’s a bug with interop shift-tab in current builds
                    request = gcnew TraversalRequest(FocusNavigationDirection::Last);
                }
                else if (!GetKeyState(VK_SHIFT) && GetFocus() == lastTabStop) {
                    request = gcnew TraversalRequest(FocusNavigationDirection::Next);
                }

                if (request != nullptr)
                    return ((IKeyboardInputSink^) this)->KeyboardInputSite->OnNoMoreTabStops(request);

            }

            // Only call IsDialogMessage for keys it will do something with.
            if (msg.message == WM_SYSKEYDOWN || msg.message == WM_KEYDOWN) {
                switch (m.wParam) {
                    case VK_TAB:
                    case VK_LEFT:
                    case VK_UP:
                    case VK_RIGHT:
                    case VK_DOWN:
                    case VK_EXECUTE:
                    case VK_RETURN:
                    case VK_ESCAPE:
                    case VK_CANCEL:
                        IsDialogMessage(dialog, &m);
                        // IsDialogMessage should be called ProcessDialogMessage --
                        // it processes messages without ever really telling you
                        // if it handled a specific message or not
                        return true;
                }
            }

            return false; // not a key we handled
        }
```

<span data-ttu-id="cb401-136">これは、いくつかのより詳細な説明を使用できるようにするために、多くのコードを 1 つのピースです。</span><span class="sxs-lookup"><span data-stu-id="cb401-136">This is a lot of code in one piece, so it could use some more detailed explanations.</span></span> <span data-ttu-id="cb401-137">最初に、コードを使用して、[!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]と[!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]マクロ; という名前のマクロが既に存在するかどうかを注意する必要がある`TranslateAccelerator`winuser.h で定義されています。</span><span class="sxs-lookup"><span data-stu-id="cb401-137">First, the code using [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] and [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] macros; you need to be aware that there is already a macro named `TranslateAccelerator`, which is defined in winuser.h:</span></span>

```cpp
#define TranslateAccelerator  TranslateAcceleratorW
```

<span data-ttu-id="cb401-138">定義するように、`TranslateAccelerator`メソッドおよび not を`TranslateAcceleratorW`メソッド。</span><span class="sxs-lookup"><span data-stu-id="cb401-138">So make sure to define a `TranslateAccelerator` method and not a `TranslateAcceleratorW` method.</span></span>

<span data-ttu-id="cb401-139">同様に、アンマネージ winuser.h MSG とマネージの両方がありますは`Microsoft::Win32::MSG`構造体。</span><span class="sxs-lookup"><span data-stu-id="cb401-139">Similarly, there is both the unmanaged winuser.h MSG and the managed `Microsoft::Win32::MSG` struct.</span></span> <span data-ttu-id="cb401-140">使用して、2 つを区別することができます、 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::`演算子。</span><span class="sxs-lookup"><span data-stu-id="cb401-140">You can disambiguate between the two using the [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::` operator.</span></span>

```cpp
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,
    ModifierKeys modifiers) override
{
    ::MSG m = ConvertMessage(msg);
}

Both MSGs have the same data, but sometimes it is easier to work with the unmanaged definition, so in this sample you can define the obvious conversion routine:

```cpp
::MSG ConvertMessage(System::Windows::Interop::MSG% msg) {
    ::MSG m;
    m.hwnd = (HWND) msg.hwnd.ToPointer();
    m.lParam = (LPARAM) msg.lParam.ToPointer();
    m.message = msg.message;
    m.wParam = (WPARAM) msg.wParam.ToPointer();

    m.time = msg.time;

    POINT pt;
    pt.x = msg.pt_x;
    pt.y = msg.pt_y;
    m.pt = pt;

    return m;
}
```

<span data-ttu-id="cb401-141">戻る`TranslateAccelerator`します。</span><span class="sxs-lookup"><span data-stu-id="cb401-141">Back to `TranslateAccelerator`.</span></span> <span data-ttu-id="cb401-142">基本的な原則は、[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]関数`IsDialogMessage`、できるだけ多くの作業を行うが`IsDialogMessage`以外のダイアログ ボックスへのアクセスはありません。</span><span class="sxs-lookup"><span data-stu-id="cb401-142">The basic principle is to call the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] function `IsDialogMessage` to do as much work as possible, but `IsDialogMessage` does not have access to anything outside the dialog.</span></span> <span data-ttu-id="cb401-143">過去のダイアログの最後のコントロールのタブ移動ときに、ダイアログの周囲のユーザー タブを実行すると、フォーカスを設定する必要があります、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]呼び出して部分`IKeyboardInputSite::OnNoMoreStops`します。</span><span class="sxs-lookup"><span data-stu-id="cb401-143">As a user tab around the dialog, when tabbing runs past the last control in our dialog, you need to set focus to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion by calling `IKeyboardInputSite::OnNoMoreStops`.</span></span>

```cpp
// Win32's IsDialogMessage() will handle most of the tabbing, but doesn't know
// what to do when it reaches the last tab stop
if (m.message == WM_KEYDOWN && m.wParam == VK_TAB) {
    HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);
    HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);
    TraversalRequest^ request = nullptr;

    if (GetKeyState(VK_SHIFT) && GetFocus() == firstTabStop) {
        request = gcnew TraversalRequest(FocusNavigationDirection::Last);
    }
    else if (!GetKeyState(VK_SHIFT) && GetFocus() ==  lastTabStop) { {
        request = gcnew TraversalRequest(FocusNavigationDirection::Next);
    }

    if (request != nullptr)
        return ((IKeyboardInputSink^) this)->KeyboardInputSite->OnNoMoreTabStops(request);
}
```

<span data-ttu-id="cb401-144">最後に、`IsDialogMessage` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cb401-144">Finally, call `IsDialogMessage`.</span></span> <span data-ttu-id="cb401-145">役割の 1 つが、`TranslateAccelerator`メソッドは、指示[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]かどうかにキーストロークを処理するかどうか。</span><span class="sxs-lookup"><span data-stu-id="cb401-145">But one of the responsibilities of a `TranslateAccelerator` method is telling [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] whether you handled the keystroke or not.</span></span> <span data-ttu-id="cb401-146">入力イベントをトンネル処理しなかった場合や、アプリケーションの残りの部分からバブルです。</span><span class="sxs-lookup"><span data-stu-id="cb401-146">If you did not handle it, the input event can tunnel and bubble through the rest of the application.</span></span> <span data-ttu-id="cb401-147">キーボード メッセージ処理の特性とでは、入力アーキテクチャの性質を公開するここでは、[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="cb401-147">Here, you will expose a quirk of keyboard messange handling and the nature of the input architecture in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].</span></span> <span data-ttu-id="cb401-148">残念ながら、`IsDialogMessage`返さない何らかの方法で特定のキーストロークを処理するかどうか。</span><span class="sxs-lookup"><span data-stu-id="cb401-148">Unfortunately, `IsDialogMessage` does not return in any way whether it handles a particular keystroke.</span></span> <span data-ttu-id="cb401-149">呼び出す、さらに悪いこと`DispatchMessage()`キーストロークを処理しないでください。</span><span class="sxs-lookup"><span data-stu-id="cb401-149">Even worse, it will call `DispatchMessage()` on keystrokes it should not handle!</span></span>  <span data-ttu-id="cb401-150">リバース エンジニア リングする必要がありますように`IsDialogMessage`、しか知らないキーを処理するために呼び出すとします。</span><span class="sxs-lookup"><span data-stu-id="cb401-150">So you will have to reverse-engineer `IsDialogMessage`, and only call it for the keys you know it will handle:</span></span>

```cpp
// Only call IsDialogMessage for keys it will do something with.
if (msg.message == WM_SYSKEYDOWN || msg.message == WM_KEYDOWN) {
    switch (m.wParam) {
        case VK_TAB:
        case VK_LEFT:
        case VK_UP:
        case VK_RIGHT:
        case VK_DOWN:
        case VK_EXECUTE:
        case VK_RETURN:
        case VK_ESCAPE:
        case VK_CANCEL:
            IsDialogMessage(dialog, &m);
            // IsDialogMessage should be called ProcessDialogMessage --
            // it processes messages without ever really telling you
            // if it handled a specific message or not
            return true;
    }
```

### <a name="override-tabinto-method-to-support-tabbing"></a><span data-ttu-id="cb401-151">この問題のメソッドをオーバーライドしてサポートのタブ移動するには</span><span class="sxs-lookup"><span data-stu-id="cb401-151">Override TabInto Method to Support Tabbing</span></span>

<span data-ttu-id="cb401-152">実装している`TranslateAccelerator`、ユーザーは、周囲 タブ ダイアログ ボックス内でボックスと、大きい値にそのタブ[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="cb401-152">Now that you have implemented `TranslateAccelerator`, a user can tab around inside the dialog box and tab out of it into the greater [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="cb401-153">ユーザーがダイアログ ボックスにタブことはできません。</span><span class="sxs-lookup"><span data-stu-id="cb401-153">But a user cannot tab back into the dialog box.</span></span> <span data-ttu-id="cb401-154">オーバーライドしている問題を解決する`TabInto`:</span><span class="sxs-lookup"><span data-stu-id="cb401-154">To solve that, you override `TabInto`:</span></span>

```cpp
public:
    virtual bool TabInto(TraversalRequest^ request) override {
        if (request->FocusNavigationDirection == FocusNavigationDirection::Last) {
            HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);
            SetFocus(lastTabStop);
        }
        else {
            HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);
            SetFocus(firstTabStop);
        }
        return true;
    }
```

<span data-ttu-id="cb401-155">`TraversalRequest`パラメーターは、タブのアクションは、タブまたは shift キーを押し タブかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="cb401-155">The `TraversalRequest` parameter tells you whether the tab action is a tab or shift tab.</span></span>

### <a name="override-onmnemonic-method-to-support-mnemonics"></a><span data-ttu-id="cb401-156">ニーモニックをサポートするために OnMnemonic メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="cb401-156">Override OnMnemonic Method to Support Mnemonics</span></span>

<span data-ttu-id="cb401-157">キーボードの処理はほぼ完了が 1 つであることはありません – ニーモニックは機能しません。</span><span class="sxs-lookup"><span data-stu-id="cb401-157">Keyboard handling is almost complete, but there is one thing missing – mnemonics do not work.</span></span> <span data-ttu-id="cb401-158">フォーカス doe がジャンプしなく-f alt キーを押すと場合、"名:"ボックスを編集します。</span><span class="sxs-lookup"><span data-stu-id="cb401-158">If a user presses alt-F, focus doe not jump to the "First name:" edit box.</span></span> <span data-ttu-id="cb401-159">そのため、オーバーライドして、`OnMnemonic`メソッド。</span><span class="sxs-lookup"><span data-stu-id="cb401-159">So, you override the `OnMnemonic` method:</span></span>

```cpp
virtual bool OnMnemonic(System::Windows::Interop::MSG% msg, ModifierKeys modifiers) override {
    ::MSG m = ConvertMessage(msg);

    // If it's one of our mnemonics, set focus to the appropriate hwnd
    if (msg.message == WM_SYSCHAR && GetKeyState(VK_MENU /*alt*/)) {
        int dialogitem = 9999;
        switch (m.wParam) {
            case 's': dialogitem = IDOK; break;
            case 'c': dialogitem = IDCANCEL; break;
            case 'f': dialogitem = IDC_EDIT1; break;
            case 'l': dialogitem = IDC_EDIT2; break;
            case 'p': dialogitem = IDC_EDIT3; break;
            case 'a': dialogitem = IDC_EDIT4; break;
            case 'i': dialogitem = IDC_EDIT5; break;
            case 't': dialogitem = IDC_EDIT6; break;
            case 'z': dialogitem = IDC_EDIT7; break;
        }
        if (dialogitem != 9999) {
            HWND hwnd = GetDlgItem(dialog, dialogitem);
            SetFocus(hwnd);
            return true;
        }
    }
    return false; // key unhandled
};
```

<span data-ttu-id="cb401-160">なぜ`IsDialogMessage`ここか?</span><span class="sxs-lookup"><span data-stu-id="cb401-160">Why not call `IsDialogMessage` here?</span></span>  <span data-ttu-id="cb401-161">これまでに通知できるようにする必要があります。 同じ問題がある[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]コードか、キーストロークが処理されるかどうかをコードと`IsDialogMessage`を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="cb401-161">You have the same issue as before--you need to be able to inform [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] code whether your code handled the keystroke or not, and `IsDialogMessage` cannot do that.</span></span> <span data-ttu-id="cb401-162">2 つ目の問題があります、ため`IsDialogMessage` ダイアログ ボックス内でフォーカスがある HWND がない場合、ニーモニックの処理を拒否します。</span><span class="sxs-lookup"><span data-stu-id="cb401-162">There is also a second issue, because `IsDialogMessage` refuses to process the mnemonic if the focused HWND is not inside the dialog box.</span></span>

### <a name="instantiate-the-hwndhost-derived-class"></a><span data-ttu-id="cb401-163">インスタンスを作成、HwndHost 派生クラス</span><span class="sxs-lookup"><span data-stu-id="cb401-163">Instantiate the HwndHost Derived Class</span></span>

<span data-ttu-id="cb401-164">最後に、これですべてのキーとタブのサポートができたら、配置できること、<xref:System.Windows.Interop.HwndHost>うち、大きい方に[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="cb401-164">Finally, now that all the key and tab support is in place, you can put your <xref:System.Windows.Interop.HwndHost> into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="cb401-165">メイン アプリケーションが記述されている場合[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]、適切な場所に配置する最も簡単な方法は、空のままにする、<xref:System.Windows.Controls.Border>要素を配置する、<xref:System.Windows.Interop.HwndHost>します。</span><span class="sxs-lookup"><span data-stu-id="cb401-165">If the main application is written in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], the easiest way to put it in the right place is to leave an empty <xref:System.Windows.Controls.Border> element where you want to put the <xref:System.Windows.Interop.HwndHost>.</span></span> <span data-ttu-id="cb401-166">ここで作成し、<xref:System.Windows.Controls.Border>という`insertHwndHostHere`:</span><span class="sxs-lookup"><span data-stu-id="cb401-166">Here you create a <xref:System.Windows.Controls.Border> named `insertHwndHostHere`:</span></span>

```xaml
<Window x:Class="WPFApplication1.Window1"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    Title="Windows Presentation Framework Application"
    Loaded="Window1_Loaded"
    >
    <StackPanel>
        <Button Content="WPF button"/>
        <Border Name="insertHwndHostHere" Height="200" Width="500"/>
        <Button Content="WPF button"/>
    </StackPanel>
</Window>
```

<span data-ttu-id="cb401-167">残っているはインスタンスを作成するコード シーケンスのことをお勧めを検索し、<xref:System.Windows.Interop.HwndHost>に接続し、<xref:System.Windows.Controls.Border>します。</span><span class="sxs-lookup"><span data-stu-id="cb401-167">Then all that remains is to find a good place in code sequence to instantiate the <xref:System.Windows.Interop.HwndHost> and connect it to the <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="cb401-168">この例では内に配置することのコンス トラクター、<xref:System.Windows.Window>クラスを派生します。</span><span class="sxs-lookup"><span data-stu-id="cb401-168">In this example, you will put it inside the constructor for the <xref:System.Windows.Window> derived class:</span></span>

```csharp
public partial class Window1 : Window {
    public Window1() {
    }

    void Window1_Loaded(object sender, RoutedEventArgs e) {
        HwndHost host = new ManagedCpp.MyHwndHost();
        insertHwndHostHere.Child = host;
    }
}
```

<span data-ttu-id="cb401-169">提示されます。</span><span class="sxs-lookup"><span data-stu-id="cb401-169">Which gives you:</span></span>

![実行されている WPF アプリのスクリーン ショット。](./media/hosting-win32-content-in-wpf/windows-presentation-foundation-application.png)

## <a name="see-also"></a><span data-ttu-id="cb401-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb401-171">See also</span></span>

- [<span data-ttu-id="cb401-172">WPF と Win32 の相互運用性</span><span class="sxs-lookup"><span data-stu-id="cb401-172">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
