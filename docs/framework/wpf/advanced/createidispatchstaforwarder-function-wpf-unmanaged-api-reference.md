---
title: 関数を呼び出す - WPF アンマネージ API リファレンス
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: e151ffa6eb5f1dc7479c699e0d7f9f3f57833ebd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174720"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="126dd-102">関数を作成します (WPF アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="126dd-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="126dd-103">この API は、Windows プレゼンテーション基盤 (WPF) インフラストラクチャをサポートし、コードから直接使用することを意図していません。</span><span class="sxs-lookup"><span data-stu-id="126dd-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="126dd-104">スレッドおよびウィンドウ管理用の Windows プレゼンテーション 基盤 (WPF) インフラストラクチャで使用されます。</span><span class="sxs-lookup"><span data-stu-id="126dd-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="126dd-105">構文</span><span class="sxs-lookup"><span data-stu-id="126dd-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="126dd-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="126dd-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="126dd-107">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="126dd-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="126dd-108">ディスパッチデリゲート</span><span class="sxs-lookup"><span data-stu-id="126dd-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="126dd-109">`IDispatch`インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="126dd-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="126dd-110">ppフォワー</span><span class="sxs-lookup"><span data-stu-id="126dd-110">ppForwarder</span></span>  
 <span data-ttu-id="126dd-111">`IDispatch`インターフェイスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="126dd-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="126dd-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="126dd-112">Requirements</span></span>  
 <span data-ttu-id="126dd-113">**プラットフォーム:**[NET Framework のシステム要件](../../get-started/system-requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="126dd-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="126dd-114">**Dll：**</span><span class="sxs-lookup"><span data-stu-id="126dd-114">**DLL:**</span></span>  
  
 <span data-ttu-id="126dd-115">NET フレームワーク 3.0 および 3.5: プレゼンテーションホストDLL.dll</span><span class="sxs-lookup"><span data-stu-id="126dd-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="126dd-116">NET フレームワーク 4 以降の場合: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="126dd-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="126dd-117">**.NET フレームワーク のバージョン:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="126dd-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="126dd-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="126dd-118">See also</span></span>

- [<span data-ttu-id="126dd-119">WPF のアンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="126dd-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
