---
title: Win32 コンテンツのホスト
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: c0c62f1999feaf591c512314515f01e83fa12591
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "86052092"
---
# <a name="hosting-win32-content-in-wpf"></a><span data-ttu-id="3a022-102">WPF での Win32 コンテンツのホスト</span><span class="sxs-lookup"><span data-stu-id="3a022-102">Hosting Win32 Content in WPF</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3a022-103">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3a022-103">Prerequisites</span></span>

<span data-ttu-id="3a022-104">「[WPF と Win32 の相互運用性](wpf-and-win32-interoperation.md)」を参照してください</span><span class="sxs-lookup"><span data-stu-id="3a022-104">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a><span data-ttu-id="3a022-105">Windows Presentation Framework (HwndHost) 内の Win32 のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="3a022-105">A Walkthrough of Win32 Inside Windows Presentation Framework (HwndHost)</span></span>

<span data-ttu-id="3a022-106">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーション内で Win32 コンテンツを再利用するには、<xref:System.Windows.Interop.HwndHost> を使用します。これは、HWND を [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] コンテンツのようにするコントロールです。</span><span class="sxs-lookup"><span data-stu-id="3a022-106">To reuse Win32 content inside [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications, use <xref:System.Windows.Interop.HwndHost>, which is a control that makes HWNDs look like [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="3a022-107"><xref:System.Windows.Interop.HwndSource> と同様に、<xref:System.Windows.Interop.HwndHost> は簡単に使用できます。<xref:System.Windows.Interop.HwndHost> から派生し、`BuildWindowCore` および `DestroyWindowCore` メソッドを実装し、<xref:System.Windows.Interop.HwndHost> 派生クラスをインスタンス化して [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーション内に配置します。</span><span class="sxs-lookup"><span data-stu-id="3a022-107">Like <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> is straightforward to use: derive from <xref:System.Windows.Interop.HwndHost> and implement `BuildWindowCore` and `DestroyWindowCore` methods, then instantiate your <xref:System.Windows.Interop.HwndHost> derived class and place it inside your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>

<span data-ttu-id="3a022-108">Win32 ロジックが既にコントロールとしてパッケージ化されている場合、`BuildWindowCore` の実装は単なる `CreateWindow` の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="3a022-108">If your Win32 logic is already packaged as a control, then your `BuildWindowCore` implementation is little more than a call to `CreateWindow`.</span></span> <span data-ttu-id="3a022-109">たとえば、C++ で Win32 LISTBOX コントロールを作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="3a022-109">For example, to create a Win32 LISTBOX control in C++:</span></span>

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

<span data-ttu-id="3a022-110">ただし、Win32 コードがそれほど自己完結型ではない場合はどうでしょうか。</span><span class="sxs-lookup"><span data-stu-id="3a022-110">But suppose the Win32 code is not quite so self-contained?</span></span> <span data-ttu-id="3a022-111">その場合は、Win32 ダイアログ ボックスを作成し、そのコンテンツをより大きな [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションに埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="3a022-111">If so, you can create a Win32 dialog box and embed its contents into a larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="3a022-112">このサンプルでは、これを Visual Studio および C++ で示していますが、別の言語またはコマンド ラインで行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="3a022-112">The sample shows this in Visual Studio and C++, although it is also possible to do this in a different language or at the command line.</span></span>

<span data-ttu-id="3a022-113">まず C++ DLL プロジェクトにコンパイルされるシンプルなダイアログから始めます。</span><span class="sxs-lookup"><span data-stu-id="3a022-113">Start with a simple dialog, which is compiled into a C++ DLL project.</span></span>

<span data-ttu-id="3a022-114">次に、より大きな [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションにダイアログを導入します。</span><span class="sxs-lookup"><span data-stu-id="3a022-114">Next, introduce the dialog into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application:</span></span>

- <span data-ttu-id="3a022-115">DLL をマネージドとしてコンパイルする (`/clr`)</span><span class="sxs-lookup"><span data-stu-id="3a022-115">Compile the DLL as managed (`/clr`)</span></span>

- <span data-ttu-id="3a022-116">ダイアログをコントロールに変換する</span><span class="sxs-lookup"><span data-stu-id="3a022-116">Turn the dialog into a control</span></span>

- <span data-ttu-id="3a022-117">`BuildWindowCore` メソッドと `DestroyWindowCore` メソッドを使用して <xref:System.Windows.Interop.HwndHost> の派生クラスを定義する</span><span class="sxs-lookup"><span data-stu-id="3a022-117">Define the derived class of <xref:System.Windows.Interop.HwndHost> with `BuildWindowCore` and `DestroyWindowCore` methods</span></span>

- <span data-ttu-id="3a022-118">ダイアログ キーを処理するために `TranslateAccelerator` メソッドをオーバーライドする</span><span class="sxs-lookup"><span data-stu-id="3a022-118">Override `TranslateAccelerator` method to handle dialog keys</span></span>

- <span data-ttu-id="3a022-119">タブ移動をサポートするために `TabInto` メソッドをオーバーライドする</span><span class="sxs-lookup"><span data-stu-id="3a022-119">Override `TabInto` method to support tabbing</span></span>

- <span data-ttu-id="3a022-120">ニーモニックをサポートするために `OnMnemonic` メソッドをオーバーライドする</span><span class="sxs-lookup"><span data-stu-id="3a022-120">Override `OnMnemonic` method to support mnemonics</span></span>

- <span data-ttu-id="3a022-121"><xref:System.Windows.Interop.HwndHost> サブクラスをインスタンス化し、適切な [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 要素の下に配置します</span><span class="sxs-lookup"><span data-stu-id="3a022-121">Instantiate the <xref:System.Windows.Interop.HwndHost> subclass and put it under the right [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element</span></span>

### <a name="turn-the-dialog-into-a-control"></a><span data-ttu-id="3a022-122">ダイアログをコントロールに変換する</span><span class="sxs-lookup"><span data-stu-id="3a022-122">Turn the Dialog into a Control</span></span>

<span data-ttu-id="3a022-123">WS_CHILD および DS_CONTROL スタイルを使用して、ダイアログ ボックスを子 HWND に変えることができます。</span><span class="sxs-lookup"><span data-stu-id="3a022-123">You can turn a dialog box into a child HWND using the WS_CHILD and DS_CONTROL styles.</span></span> <span data-ttu-id="3a022-124">ダイアログが定義されているリソース ファイル (.rc) に移動し、ダイアログの定義の先頭を見つけます。</span><span class="sxs-lookup"><span data-stu-id="3a022-124">Go into the resource file (.rc) where the dialog is defined, and find the beginning of the definition of the dialog:</span></span>

```text
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU
```

<span data-ttu-id="3a022-125">2 行目を次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="3a022-125">Change the second line to:</span></span>

```text
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL
```

<span data-ttu-id="3a022-126">このアクションでは、自己完結型のコントロールに完全にパッケージ化されません。Win32 で特定のメッセージを処理できるように、`IsDialogMessage()` を呼び出す必要がありますが、このコントロールの変更により、これらのコントロールを別の HWND 内に簡単に配置できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3a022-126">This action does not fully package it into a self-contained control; you still need to call `IsDialogMessage()` so Win32 can process certain messages, but the control change does provide a straightforward way of putting those controls inside another HWND.</span></span>

## <a name="subclass-hwndhost"></a><span data-ttu-id="3a022-127">サブクラス HwndHost</span><span class="sxs-lookup"><span data-stu-id="3a022-127">Subclass HwndHost</span></span>

<span data-ttu-id="3a022-128">次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="3a022-128">Import the following namespaces:</span></span>

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

<span data-ttu-id="3a022-129">次に、<xref:System.Windows.Interop.HwndHost> の派生クラスを作成し、`BuildWindowCore` および `DestroyWindowCore` メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="3a022-129">Then create a derived class of <xref:System.Windows.Interop.HwndHost> and override the `BuildWindowCore` and `DestroyWindowCore` methods:</span></span>

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

<span data-ttu-id="3a022-130">ここでは、`CreateDialog` を使用して、実際にコントロールであるダイアログ ボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="3a022-130">Here you use the `CreateDialog` to create the dialog box that is really a control.</span></span> <span data-ttu-id="3a022-131">これは DLL 内で呼び出される最初のメソッドの 1 つであるため、後で定義する `InitializeGlobals()` という関数を呼び出して、標準の Win32 初期化を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a022-131">Since this is one of the first methods called inside the DLL, you should also do some standard Win32 initialization by calling a function you will define later, called `InitializeGlobals()`:</span></span>

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

### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a><span data-ttu-id="3a022-132">ダイアログキーを処理するために TranslateAccelerator メソッドをオーバーライドする</span><span class="sxs-lookup"><span data-stu-id="3a022-132">Override TranslateAccelerator Method to Handle Dialog Keys</span></span>

<span data-ttu-id="3a022-133">ここでこのサンプルを実行すると、ダイアログ コントロールが表示されますが、ダイアログ ボックスを機能するダイアログ ボックスにするキーボード処理はすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="3a022-133">If you ran this sample now, you would get a dialog control that displays, but it would ignore all of the keyboard processing that makes a dialog box a functional dialog box.</span></span> <span data-ttu-id="3a022-134">ここで、`TranslateAccelerator` 実装 (<xref:System.Windows.Interop.HwndHost> に実装されているインターフェイスである `IKeyboardInputSink` から継承されます) をオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a022-134">You should now override the `TranslateAccelerator` implementation (which comes from `IKeyboardInputSink`, an interface that <xref:System.Windows.Interop.HwndHost> implements).</span></span> <span data-ttu-id="3a022-135">このメソッドは、アプリケーションが WM_KEYDOWN および WM_SYSKEYDOWN を受け取ったときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3a022-135">This method gets called when the application receives WM_KEYDOWN and WM_SYSKEYDOWN.</span></span>

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

<span data-ttu-id="3a022-136">これには多くのコードが 1 つにまとめられているため、より詳細な説明を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3a022-136">This is a lot of code in one piece, so it could use some more detailed explanations.</span></span> <span data-ttu-id="3a022-137">1 つ目は、C++ および C++ マクロを使用するコードです。winuser.h で定義されている `TranslateAccelerator` という名前のマクロが既に存在することに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a022-137">First, the code using C++ and C++ macros; you need to be aware that there is already a macro named `TranslateAccelerator`, which is defined in winuser.h:</span></span>

```cpp
#define TranslateAccelerator  TranslateAcceleratorW
```

<span data-ttu-id="3a022-138">そのため、`TranslateAcceleratorW` メソッドではなく、必ず `TranslateAccelerator` メソッドを定義してください。</span><span class="sxs-lookup"><span data-stu-id="3a022-138">So make sure to define a `TranslateAccelerator` method and not a `TranslateAcceleratorW` method.</span></span>

<span data-ttu-id="3a022-139">同様に、アンマネージド winuser.h MSG とマネージド `Microsoft::Win32::MSG` 構造体の両方があります。</span><span class="sxs-lookup"><span data-stu-id="3a022-139">Similarly, there is both the unmanaged winuser.h MSG and the managed `Microsoft::Win32::MSG` struct.</span></span> <span data-ttu-id="3a022-140">C++ の `::` 演算子を使用して、2 つを区別することができます。</span><span class="sxs-lookup"><span data-stu-id="3a022-140">You can disambiguate between the two using the C++ `::` operator.</span></span>

```cpp
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,
    ModifierKeys modifiers) override
{
    ::MSG m = ConvertMessage(msg);
}
```

<span data-ttu-id="3a022-141">いずれの MSG にも同じデータがありますが、アンマネージドの定義を使用した方が簡単なときがあります。そのため、このサンプルでは、見てすぐわかる変換ルーチンを定義できます。</span><span class="sxs-lookup"><span data-stu-id="3a022-141">Both MSGs have the same data, but sometimes it is easier to work with the unmanaged definition, so in this sample you can define the obvious conversion routine:</span></span>

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

<span data-ttu-id="3a022-142">`TranslateAccelerator` に戻ります。</span><span class="sxs-lookup"><span data-stu-id="3a022-142">Back to `TranslateAccelerator`.</span></span> <span data-ttu-id="3a022-143">基本的な原則は、できるだけ多くの作業を行うために Win32 関数 `IsDialogMessage` を呼び出すことですが、`IsDialogMessage` ではダイアログの外部にはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="3a022-143">The basic principle is to call the Win32 function `IsDialogMessage` to do as much work as possible, but `IsDialogMessage` does not have access to anything outside the dialog.</span></span> <span data-ttu-id="3a022-144">ユーザーが Tab キーを使ってダイアログ内を移動するときに、タブ移動がダイアログの最後のコントロールを過ぎた場合に、`IKeyboardInputSite::OnNoMoreStops` を呼び出してフォーカスを [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] の部分に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a022-144">As a user tab around the dialog, when tabbing runs past the last control in our dialog, you need to set focus to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion by calling `IKeyboardInputSite::OnNoMoreStops`.</span></span>

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

<span data-ttu-id="3a022-145">最後に、`IsDialogMessage` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3a022-145">Finally, call `IsDialogMessage`.</span></span> <span data-ttu-id="3a022-146">ただし、`TranslateAccelerator` メソッドの役割の 1 つは、キー入力を処理したかどうかを [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] に伝えることです。</span><span class="sxs-lookup"><span data-stu-id="3a022-146">But one of the responsibilities of a `TranslateAccelerator` method is telling [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] whether you handled the keystroke or not.</span></span> <span data-ttu-id="3a022-147">これを処理しなかった場合、アプリケーションの残りの部分で、入力イベントのトンネリングとバブリングが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3a022-147">If you did not handle it, the input event can tunnel and bubble through the rest of the application.</span></span> <span data-ttu-id="3a022-148">ここでは、キーボードのメッセージ処理の癖と Win32 の入力アーキテクチャの性質を明らかにします。</span><span class="sxs-lookup"><span data-stu-id="3a022-148">Here, you will expose a quirk of keyboard messange handling and the nature of the input architecture in Win32.</span></span> <span data-ttu-id="3a022-149">残念ながら、どのような方法でも、`IsDialogMessage` から特定のキー入力を処理するかどうかは返されません。</span><span class="sxs-lookup"><span data-stu-id="3a022-149">Unfortunately, `IsDialogMessage` does not return in any way whether it handles a particular keystroke.</span></span> <span data-ttu-id="3a022-150">さらに悪いことに、処理してはならないキー入力で `DispatchMessage()` が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3a022-150">Even worse, it will call `DispatchMessage()` on keystrokes it should not handle!</span></span>  <span data-ttu-id="3a022-151">そのため、`IsDialogMessage` をリバースエンジニアリングして、処理することがわかっているキーに対してのみ呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a022-151">So you will have to reverse-engineer `IsDialogMessage`, and only call it for the keys you know it will handle:</span></span>

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

### <a name="override-tabinto-method-to-support-tabbing"></a><span data-ttu-id="3a022-152">タブ移動をサポートするために TabInto メソッドをオーバーライドする</span><span class="sxs-lookup"><span data-stu-id="3a022-152">Override TabInto Method to Support Tabbing</span></span>

<span data-ttu-id="3a022-153">これで `TranslateAccelerator` を実装したので、ユーザーは Tab キーを使ってダイアログ ボックス内を移動し、そこからより大きな [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションにタブ移動できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3a022-153">Now that you have implemented `TranslateAccelerator`, a user can tab around inside the dialog box and tab out of it into the greater [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="3a022-154">ただし、ユーザーがダイアログ ボックスに戻ることはできません。</span><span class="sxs-lookup"><span data-stu-id="3a022-154">But a user cannot tab back into the dialog box.</span></span> <span data-ttu-id="3a022-155">これを解決するには、`TabInto` をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="3a022-155">To solve that, you override `TabInto`:</span></span>

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

<span data-ttu-id="3a022-156">`TraversalRequest` パラメーターを使用すると、タブ操作が Tab キーか Shift + Tab キーのどちらであるかがわかります。</span><span class="sxs-lookup"><span data-stu-id="3a022-156">The `TraversalRequest` parameter tells you whether the tab action is a tab or shift tab.</span></span>

### <a name="override-onmnemonic-method-to-support-mnemonics"></a><span data-ttu-id="3a022-157">ニーモニックをサポートするするために OnMnemonic メソッドをオーバーライドする</span><span class="sxs-lookup"><span data-stu-id="3a022-157">Override OnMnemonic Method to Support Mnemonics</span></span>

<span data-ttu-id="3a022-158">キーボードの処理はほぼ完了していますが、不足していることが 1 つあります。ニーモニックが機能しないことです。</span><span class="sxs-lookup"><span data-stu-id="3a022-158">Keyboard handling is almost complete, but there is one thing missing – mnemonics do not work.</span></span> <span data-ttu-id="3a022-159">ユーザーが Alt + F キーを押した場合、フォーカスは [First name:]\(名\) 編集ボックスにジャンプしません。</span><span class="sxs-lookup"><span data-stu-id="3a022-159">If a user presses alt-F, focus doe not jump to the "First name:" edit box.</span></span> <span data-ttu-id="3a022-160">そのため、`OnMnemonic` メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="3a022-160">So, you override the `OnMnemonic` method:</span></span>

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

<span data-ttu-id="3a022-161">ここで `IsDialogMessage` を呼び出してみましょう。</span><span class="sxs-lookup"><span data-stu-id="3a022-161">Why not call `IsDialogMessage` here?</span></span>  <span data-ttu-id="3a022-162">前と同じ問題があります。コードでキー入力を処理されたかどうかを [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] コードに通知する必要がありますが、`IsDialogMessage` ではそれを行うことができません。</span><span class="sxs-lookup"><span data-stu-id="3a022-162">You have the same issue as before--you need to be able to inform [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] code whether your code handled the keystroke or not, and `IsDialogMessage` cannot do that.</span></span> <span data-ttu-id="3a022-163">また、2 つ目の問題もあります。フォーカスされた HWND がダイアログ ボックス内にない場合、`IsDialogMessage` ではニーモニックの処理が拒否されるためです。</span><span class="sxs-lookup"><span data-stu-id="3a022-163">There is also a second issue, because `IsDialogMessage` refuses to process the mnemonic if the focused HWND is not inside the dialog box.</span></span>

### <a name="instantiate-the-hwndhost-derived-class"></a><span data-ttu-id="3a022-164">HwndHost 派生クラスをインスタンス化する</span><span class="sxs-lookup"><span data-stu-id="3a022-164">Instantiate the HwndHost Derived Class</span></span>

<span data-ttu-id="3a022-165">キーとタブが適切にサポートされたので、最後に、<xref:System.Windows.Interop.HwndHost> をより大きな[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションに配置できます。</span><span class="sxs-lookup"><span data-stu-id="3a022-165">Finally, now that all the key and tab support is in place, you can put your <xref:System.Windows.Interop.HwndHost> into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="3a022-166">メイン アプリケーションが [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] で記述されている場合、適切な場所に配置する最も簡単な方法は、<xref:System.Windows.Interop.HwndHost> を配置する場所に空の <xref:System.Windows.Controls.Border> 要素を配置しておくことです。</span><span class="sxs-lookup"><span data-stu-id="3a022-166">If the main application is written in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], the easiest way to put it in the right place is to leave an empty <xref:System.Windows.Controls.Border> element where you want to put the <xref:System.Windows.Interop.HwndHost>.</span></span> <span data-ttu-id="3a022-167">ここでは、`insertHwndHostHere` という名前の <xref:System.Windows.Controls.Border> を作成します。</span><span class="sxs-lookup"><span data-stu-id="3a022-167">Here you create a <xref:System.Windows.Controls.Border> named `insertHwndHostHere`:</span></span>

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

<span data-ttu-id="3a022-168">残りの作業は、コード シーケンス内の適切な場所を見つけて <xref:System.Windows.Interop.HwndHost> をインスタンス化し、それを <xref:System.Windows.Controls.Border> に接続することだけです。</span><span class="sxs-lookup"><span data-stu-id="3a022-168">Then all that remains is to find a good place in code sequence to instantiate the <xref:System.Windows.Interop.HwndHost> and connect it to the <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="3a022-169">この例では、<xref:System.Windows.Window> 派生クラスのコンストラクター内に配置します。</span><span class="sxs-lookup"><span data-stu-id="3a022-169">In this example, you will put it inside the constructor for the <xref:System.Windows.Window> derived class:</span></span>

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

<span data-ttu-id="3a022-170">次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3a022-170">Which gives you:</span></span>

![実行中の WPF アプリのスクリーンショット。](./media/hosting-win32-content-in-wpf/windows-presentation-foundation-application.png)

## <a name="see-also"></a><span data-ttu-id="3a022-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a022-172">See also</span></span>

- [<span data-ttu-id="3a022-173">WPF と Win32 の相互運用性</span><span class="sxs-lookup"><span data-stu-id="3a022-173">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
