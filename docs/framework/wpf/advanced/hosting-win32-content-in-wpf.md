---
title: WPF での Win32 コンテンツのホスト
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: ee260d58cdb4dc971fc32ca5c889b459b6a48489
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484735"
---
# <a name="hosting-win32-content-in-wpf"></a><span data-ttu-id="f7260-102">WPF での Win32 コンテンツのホスト</span><span class="sxs-lookup"><span data-stu-id="f7260-102">Hosting Win32 Content in WPF</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f7260-103">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f7260-103">Prerequisites</span></span>

<span data-ttu-id="f7260-104">「 [WPF と Win32 の相互運用」を](wpf-and-win32-interoperation.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7260-104">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a><span data-ttu-id="f7260-105">Windows Presentation Framework 内部の Win32 のチュートリアル (HwndHost)</span><span class="sxs-lookup"><span data-stu-id="f7260-105">A Walkthrough of Win32 Inside Windows Presentation Framework (HwndHost)</span></span>

<span data-ttu-id="f7260-106">アプリケーション内[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]でコンテンツを再利用<xref:System.Windows.Interop.HwndHost>するには、を使用します。これ[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]は、hwnd をコンテンツのように表示するコントロールです。</span><span class="sxs-lookup"><span data-stu-id="f7260-106">To reuse [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] content inside [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications, use <xref:System.Windows.Interop.HwndHost>, which is a control that makes HWNDs look like [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="f7260-107">と<xref:System.Windows.Interop.HwndSource>同様<xref:System.Windows.Interop.HwndHost>に、は簡単に使用でき<xref:System.Windows.Interop.HwndHost>ます。 `BuildWindowCore`から`DestroyWindowCore`派生し、メソッドを<xref:System.Windows.Interop.HwndHost>実装してから、派生クラス[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]をインスタンス化し、その中に配置します。適用.</span><span class="sxs-lookup"><span data-stu-id="f7260-107">Like <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> is straightforward to use: derive from <xref:System.Windows.Interop.HwndHost> and implement `BuildWindowCore` and `DestroyWindowCore` methods, then instantiate your <xref:System.Windows.Interop.HwndHost> derived class and place it inside your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>

<span data-ttu-id="f7260-108">ロジックが既にコントロールとしてパッケージ化され`BuildWindowCore`ている場合、の実装はの`CreateWindow`呼び出しよりもわずかです。 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7260-108">If your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] logic is already packaged as a control, then your `BuildWindowCore` implementation is little more than a call to `CreateWindow`.</span></span> <span data-ttu-id="f7260-109">たとえば、でC++LISTBOX コントロールを[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f7260-109">For example, to create a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] LISTBOX control in C++:</span></span>

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

<span data-ttu-id="f7260-110">しかし、コード[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]がそれほど自己完結していないとしたら、</span><span class="sxs-lookup"><span data-stu-id="f7260-110">But suppose the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] code is not quite so self-contained?</span></span> <span data-ttu-id="f7260-111">その場合は、ダイアログボックスを[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]作成し、その内容をより大きな[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーションに埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="f7260-111">If so, you can create a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog box and embed its contents into a larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="f7260-112">このサンプルでは、 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]とC++でこれを示していますが、別の言語またはコマンドラインでこれを行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="f7260-112">The sample shows this in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] and C++, although it is also possible to do this in a different language or at the command line.</span></span>

<span data-ttu-id="f7260-113">[!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]プロジェクトにC++コンパイルされた単純なダイアログから始めます。</span><span class="sxs-lookup"><span data-stu-id="f7260-113">Start with a simple dialog, which is compiled into a C++ [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] project.</span></span>

<span data-ttu-id="f7260-114">次に、大規模[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]なアプリケーションにダイアログを導入します。</span><span class="sxs-lookup"><span data-stu-id="f7260-114">Next, introduce the dialog into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application:</span></span>

- <span data-ttu-id="f7260-115">をマネージ[!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] (`/clr`) としてコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="f7260-115">Compile the [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] as managed (`/clr`)</span></span>

- <span data-ttu-id="f7260-116">ダイアログをコントロールに変換する</span><span class="sxs-lookup"><span data-stu-id="f7260-116">Turn the dialog into a control</span></span>

- <span data-ttu-id="f7260-117">メソッドとメソッドを使用<xref:System.Windows.Interop.HwndHost> `BuildWindowCore`して`DestroyWindowCore` 、の派生クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="f7260-117">Define the derived class of <xref:System.Windows.Interop.HwndHost> with `BuildWindowCore` and `DestroyWindowCore` methods</span></span>

- <span data-ttu-id="f7260-118">メソッド`TranslateAccelerator`をオーバーライドしてダイアログキーを処理します</span><span class="sxs-lookup"><span data-stu-id="f7260-118">Override `TranslateAccelerator` method to handle dialog keys</span></span>

- <span data-ttu-id="f7260-119">Tab `TabInto`キーをサポートするためのオーバーライドメソッド</span><span class="sxs-lookup"><span data-stu-id="f7260-119">Override `TabInto` method to support tabbing</span></span>

- <span data-ttu-id="f7260-120">ニーモニック`OnMnemonic`をサポートするオーバーライドメソッド</span><span class="sxs-lookup"><span data-stu-id="f7260-120">Override `OnMnemonic` method to support mnemonics</span></span>

- <span data-ttu-id="f7260-121">サブクラス<xref:System.Windows.Interop.HwndHost>をインスタンス化し、右側[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]の要素の下に配置する</span><span class="sxs-lookup"><span data-stu-id="f7260-121">Instantiate the <xref:System.Windows.Interop.HwndHost> subclass and put it under the right [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element</span></span>

### <a name="turn-the-dialog-into-a-control"></a><span data-ttu-id="f7260-122">ダイアログをコントロールに変換する</span><span class="sxs-lookup"><span data-stu-id="f7260-122">Turn the Dialog into a Control</span></span>

<span data-ttu-id="f7260-123">WS_CHILD スタイルと DS_CONTROL スタイルを使用して、ダイアログボックスを子 HWND にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f7260-123">You can turn a dialog box into a child HWND using the WS_CHILD and DS_CONTROL styles.</span></span> <span data-ttu-id="f7260-124">ダイアログが定義されているリソースファイル (.rc) に移動し、ダイアログの定義の先頭を見つけます。</span><span class="sxs-lookup"><span data-stu-id="f7260-124">Go into the resource file (.rc) where the dialog is defined, and find the beginning of the definition of the dialog:</span></span>

```
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU
```

<span data-ttu-id="f7260-125">2番目の行を次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="f7260-125">Change the second line to:</span></span>

```
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL
```

<span data-ttu-id="f7260-126">この操作では、自己完結型のコントロールに完全にパッケージ化されません。では、特定の`IsDialogMessage()`メッセージ[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]を処理できるようにを呼び出す必要がありますが、コントロールを変更すると、そのコントロールを別の HWND 内に簡単に配置できます。</span><span class="sxs-lookup"><span data-stu-id="f7260-126">This action does not fully package it into a self-contained control; you still need to call `IsDialogMessage()` so [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] can process certain messages, but the control change does provide a straightforward way of putting those controls inside another HWND.</span></span>

## <a name="subclass-hwndhost"></a><span data-ttu-id="f7260-127">サブクラス HwndHost</span><span class="sxs-lookup"><span data-stu-id="f7260-127">Subclass HwndHost</span></span>

<span data-ttu-id="f7260-128">次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="f7260-128">Import the following namespaces:</span></span>

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

<span data-ttu-id="f7260-129">次に、の<xref:System.Windows.Interop.HwndHost>派生クラスを作成し、メソッド`BuildWindowCore`と`DestroyWindowCore`メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="f7260-129">Then create a derived class of <xref:System.Windows.Interop.HwndHost> and override the `BuildWindowCore` and `DestroyWindowCore` methods:</span></span>

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

<span data-ttu-id="f7260-130">ここでは、 `CreateDialog`を使用して、実際にはコントロールであるダイアログボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7260-130">Here you use the `CreateDialog` to create the dialog box that is really a control.</span></span> <span data-ttu-id="f7260-131">これはの[!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]内部で呼び出された最初のメソッドの1つであるため、 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]後`InitializeGlobals()`で定義する関数を呼び出すことによって、標準の初期化も実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7260-131">Since this is one of the first methods called inside the [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], you should also do some standard [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] initialization by calling a function you will define later, called `InitializeGlobals()`:</span></span>

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

### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a><span data-ttu-id="f7260-132">TranslateAccelerator メソッドをオーバーライドしてダイアログキーを処理します</span><span class="sxs-lookup"><span data-stu-id="f7260-132">Override TranslateAccelerator Method to Handle Dialog Keys</span></span>

<span data-ttu-id="f7260-133">このサンプルを今実行した場合、ダイアログコントロールが表示されますが、ダイアログボックスを機能させるためのダイアログボックスを表示するすべてのキーボード処理が無視されます。</span><span class="sxs-lookup"><span data-stu-id="f7260-133">If you ran this sample now, you would get a dialog control that displays, but it would ignore all of the keyboard processing that makes a dialog box a functional dialog box.</span></span> <span data-ttu-id="f7260-134">ここで`TranslateAccelerator` `IKeyboardInputSink`、実装 (を実装する<xref:System.Windows.Interop.HwndHost>インターフェイス) をオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7260-134">You should now override the `TranslateAccelerator` implementation (which comes from `IKeyboardInputSink`, an interface that <xref:System.Windows.Interop.HwndHost> implements).</span></span> <span data-ttu-id="f7260-135">このメソッドは、アプリケーションが WM_KEYDOWN と WM_SYSKEYDOWN を受け取ると呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f7260-135">This method gets called when the application receives WM_KEYDOWN and WM_SYSKEYDOWN.</span></span>

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

<span data-ttu-id="f7260-136">これは、1つの部分に多くのコードがあるため、より詳細な説明を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7260-136">This is a lot of code in one piece, so it could use some more detailed explanations.</span></span> <span data-ttu-id="f7260-137">まず、マクロとC++ C++マクロを使用するコードです。winuser. h で定義されているという`TranslateAccelerator`名前のマクロが既に存在することに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7260-137">First, the code using C++ and C++ macros; you need to be aware that there is already a macro named `TranslateAccelerator`, which is defined in winuser.h:</span></span>

```cpp
#define TranslateAccelerator  TranslateAcceleratorW
```

<span data-ttu-id="f7260-138">したがって、メソッドでは`TranslateAccelerator` `TranslateAcceleratorW`なく、メソッドを定義してください。</span><span class="sxs-lookup"><span data-stu-id="f7260-138">So make sure to define a `TranslateAccelerator` method and not a `TranslateAcceleratorW` method.</span></span>

<span data-ttu-id="f7260-139">同様に、アンマネージ winuser .h メッセージとマネージ`Microsoft::Win32::MSG`構造体の両方があります。</span><span class="sxs-lookup"><span data-stu-id="f7260-139">Similarly, there is both the unmanaged winuser.h MSG and the managed `Microsoft::Win32::MSG` struct.</span></span> <span data-ttu-id="f7260-140">`::`演算子を使用してC++ 、2つを明確に区別できます。</span><span class="sxs-lookup"><span data-stu-id="f7260-140">You can disambiguate between the two using the C++ `::` operator.</span></span>

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

<span data-ttu-id="f7260-141">に`TranslateAccelerator`戻ります。</span><span class="sxs-lookup"><span data-stu-id="f7260-141">Back to `TranslateAccelerator`.</span></span> <span data-ttu-id="f7260-142">基本的な原則は、 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]関数`IsDialogMessage`を呼び出して、可能な限り多くの作業を`IsDialogMessage`行うことですが、ダイアログの外部にアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f7260-142">The basic principle is to call the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] function `IsDialogMessage` to do as much work as possible, but `IsDialogMessage` does not have access to anything outside the dialog.</span></span> <span data-ttu-id="f7260-143">ダイアログの周囲のユーザータブとして、ダイアログの最後のコントロールの後で tab キーを実行する場合は、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]を呼び出し`IKeyboardInputSite::OnNoMoreStops`て、その部分にフォーカスを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7260-143">As a user tab around the dialog, when tabbing runs past the last control in our dialog, you need to set focus to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion by calling `IKeyboardInputSite::OnNoMoreStops`.</span></span>

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

<span data-ttu-id="f7260-144">最後に、`IsDialogMessage` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f7260-144">Finally, call `IsDialogMessage`.</span></span> <span data-ttu-id="f7260-145">しかし、 `TranslateAccelerator`メソッドの役割の1つは、 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]キーストロークを処理したかどうかを通知することです。</span><span class="sxs-lookup"><span data-stu-id="f7260-145">But one of the responsibilities of a `TranslateAccelerator` method is telling [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] whether you handled the keystroke or not.</span></span> <span data-ttu-id="f7260-146">処理しなかった場合、入力イベントは、アプリケーションの他の部分をトンネルおよびバブルできます。</span><span class="sxs-lookup"><span data-stu-id="f7260-146">If you did not handle it, the input event can tunnel and bubble through the rest of the application.</span></span> <span data-ttu-id="f7260-147">ここでは、のキーボード messange 処理の特性と、の入力アーキテクチャ[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]の性質を公開します。</span><span class="sxs-lookup"><span data-stu-id="f7260-147">Here, you will expose a quirk of keyboard messange handling and the nature of the input architecture in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].</span></span> <span data-ttu-id="f7260-148">残念ながら`IsDialogMessage` 、は、特定のキー入力を処理するかどうかを何も返しません。</span><span class="sxs-lookup"><span data-stu-id="f7260-148">Unfortunately, `IsDialogMessage` does not return in any way whether it handles a particular keystroke.</span></span> <span data-ttu-id="f7260-149">さらに悪いことに、 `DispatchMessage()`キーストロークを処理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f7260-149">Even worse, it will call `DispatchMessage()` on keystrokes it should not handle!</span></span>  <span data-ttu-id="f7260-150">そのため、リバースエンジニアリング`IsDialogMessage`を行う必要があります。これは、処理されることがわかっているキーに対してのみ呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7260-150">So you will have to reverse-engineer `IsDialogMessage`, and only call it for the keys you know it will handle:</span></span>

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

### <a name="override-tabinto-method-to-support-tabbing"></a><span data-ttu-id="f7260-151">タブ移動をサポートするために TabInto メソッドをオーバーライドする</span><span class="sxs-lookup"><span data-stu-id="f7260-151">Override TabInto Method to Support Tabbing</span></span>

<span data-ttu-id="f7260-152">実装`TranslateAccelerator`が完了したので、ユーザーはダイアログボックス内を tab キーを使用して、より大きな[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーションに tab キーを移動できます。</span><span class="sxs-lookup"><span data-stu-id="f7260-152">Now that you have implemented `TranslateAccelerator`, a user can tab around inside the dialog box and tab out of it into the greater [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="f7260-153">ただし、ユーザーがダイアログボックスに戻ることはできません。</span><span class="sxs-lookup"><span data-stu-id="f7260-153">But a user cannot tab back into the dialog box.</span></span> <span data-ttu-id="f7260-154">これを解決するには`TabInto`、次のようにオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="f7260-154">To solve that, you override `TabInto`:</span></span>

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

<span data-ttu-id="f7260-155">パラメーター `TraversalRequest`を指定すると、タブ操作がタブまたは shift タブのどちらであるかがわかります。</span><span class="sxs-lookup"><span data-stu-id="f7260-155">The `TraversalRequest` parameter tells you whether the tab action is a tab or shift tab.</span></span>

### <a name="override-onmnemonic-method-to-support-mnemonics"></a><span data-ttu-id="f7260-156">OnMnemonic メソッドをオーバーライドしてニーモニックをサポートする</span><span class="sxs-lookup"><span data-stu-id="f7260-156">Override OnMnemonic Method to Support Mnemonics</span></span>

<span data-ttu-id="f7260-157">キーボードの処理はほぼ完了していますが、不足しているものがあります。ニーモニックが機能しません。</span><span class="sxs-lookup"><span data-stu-id="f7260-157">Keyboard handling is almost complete, but there is one thing missing – mnemonics do not work.</span></span> <span data-ttu-id="f7260-158">ユーザーが alt キーを押しながら F キーを押すと、"First name:" という編集ボックスにフォーカスが移動します。</span><span class="sxs-lookup"><span data-stu-id="f7260-158">If a user presses alt-F, focus doe not jump to the "First name:" edit box.</span></span> <span data-ttu-id="f7260-159">そのため、 `OnMnemonic`メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="f7260-159">So, you override the `OnMnemonic` method:</span></span>

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

<span data-ttu-id="f7260-160">ここでは`IsDialogMessage`何を呼ぶのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="f7260-160">Why not call `IsDialogMessage` here?</span></span>  <span data-ttu-id="f7260-161">前と同じ問題が発生しています。コードでキー入力が[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]処理されたかどうか`IsDialogMessage`をコードに通知できる必要があり、そうすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f7260-161">You have the same issue as before--you need to be able to inform [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] code whether your code handled the keystroke or not, and `IsDialogMessage` cannot do that.</span></span> <span data-ttu-id="f7260-162">また、は、フォーカスされて`IsDialogMessage`いる HWND がダイアログボックス内にない場合にニーモニックの処理が拒否されるため、2つ目の問題もあります。</span><span class="sxs-lookup"><span data-stu-id="f7260-162">There is also a second issue, because `IsDialogMessage` refuses to process the mnemonic if the focused HWND is not inside the dialog box.</span></span>

### <a name="instantiate-the-hwndhost-derived-class"></a><span data-ttu-id="f7260-163">HwndHost 派生クラスをインスタンス化する</span><span class="sxs-lookup"><span data-stu-id="f7260-163">Instantiate the HwndHost Derived Class</span></span>

<span data-ttu-id="f7260-164">最後に、すべてのキーとタブのサポートが整ったので、をより<xref:System.Windows.Interop.HwndHost>大きな[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーションに配置できます。</span><span class="sxs-lookup"><span data-stu-id="f7260-164">Finally, now that all the key and tab support is in place, you can put your <xref:System.Windows.Interop.HwndHost> into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="f7260-165">メインアプリケーションがに[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]記述されている場合、適切な場所に配置する最も簡単な方法は、 <xref:System.Windows.Controls.Border> <xref:System.Windows.Interop.HwndHost>を配置する場所に空の要素を残しておくことです。</span><span class="sxs-lookup"><span data-stu-id="f7260-165">If the main application is written in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], the easiest way to put it in the right place is to leave an empty <xref:System.Windows.Controls.Border> element where you want to put the <xref:System.Windows.Interop.HwndHost>.</span></span> <span data-ttu-id="f7260-166">ここでは、 <xref:System.Windows.Controls.Border>と`insertHwndHostHere`いう名前のを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7260-166">Here you create a <xref:System.Windows.Controls.Border> named `insertHwndHostHere`:</span></span>

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

<span data-ttu-id="f7260-167">次に、 <xref:System.Windows.Interop.HwndHost>をインスタンス化してに接続<xref:System.Windows.Controls.Border>するためのコードシーケンス内の適切な場所を見つけます。</span><span class="sxs-lookup"><span data-stu-id="f7260-167">Then all that remains is to find a good place in code sequence to instantiate the <xref:System.Windows.Interop.HwndHost> and connect it to the <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="f7260-168">この例では、 <xref:System.Windows.Window>派生クラスのコンストラクター内に配置します。</span><span class="sxs-lookup"><span data-stu-id="f7260-168">In this example, you will put it inside the constructor for the <xref:System.Windows.Window> derived class:</span></span>

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

<span data-ttu-id="f7260-169">次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f7260-169">Which gives you:</span></span>

![実行中の WPF アプリのスクリーンショット。](./media/hosting-win32-content-in-wpf/windows-presentation-foundation-application.png)

## <a name="see-also"></a><span data-ttu-id="f7260-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7260-171">See also</span></span>

- [<span data-ttu-id="f7260-172">WPF と Win32 の相互運用性</span><span class="sxs-lookup"><span data-stu-id="f7260-172">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
