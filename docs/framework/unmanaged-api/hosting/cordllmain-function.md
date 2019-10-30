---
title: _CorDllMain 関数
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
ms.openlocfilehash: f60f159ab4770023cee7123b39109040243e1ccd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136972"
---
# <a name="_cordllmain-function"></a><span data-ttu-id="2976f-102">\_CorDllMain 関数</span><span class="sxs-lookup"><span data-stu-id="2976f-102">\_CorDllMain Function</span></span>

<span data-ttu-id="2976f-103">共通言語ランタイム (CLR) を初期化し、DLL アセンブリの CLR ヘッダー内のマネージエントリポイントを検索して、実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="2976f-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2976f-104">構文</span><span class="sxs-lookup"><span data-stu-id="2976f-104">Syntax</span></span>  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2976f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2976f-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="2976f-106">から読み込まれたモジュールのインスタンスハンドル。</span><span class="sxs-lookup"><span data-stu-id="2976f-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="2976f-107">からDLL のエントリポイント関数が呼び出される理由を示します。</span><span class="sxs-lookup"><span data-stu-id="2976f-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="2976f-108">このパラメーターには、次のいずれかの値を指定できます: DLL\_PROCESS_ATTACH、DLL\_スレッド\_アタッチ、DLL\_スレッド\_アタッチ、または DLL\_プロセス\_デタッチします。</span><span class="sxs-lookup"><span data-stu-id="2976f-108">This parameter can be one of the following values: DLL\_PROCESS_ATTACH, DLL\_THREAD\_ATTACH, DLL\_THREAD\_ATTACH, or DLL\_PROCESS\_DETACH.</span></span> <span data-ttu-id="2976f-109">これらの値の詳細については、Platform SDK の `DllMain` のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2976f-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="2976f-110">から未使用.</span><span class="sxs-lookup"><span data-stu-id="2976f-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2976f-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="2976f-111">Return Value</span></span>  
 <span data-ttu-id="2976f-112">このメソッドは、成功した場合は `true` を返し、エラーが発生した場合は `false` を返します。</span><span class="sxs-lookup"><span data-stu-id="2976f-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2976f-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="2976f-113">Remarks</span></span>  
 <span data-ttu-id="2976f-114">この関数は、DLL アセンブリのオペレーティングシステムローダーによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2976f-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="2976f-115">実行可能アセンブリの場合、ローダーは代わりに[\_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2976f-115">For executable assemblies, the loader calls the [\_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="2976f-116">オペレーティングシステムローダーは、DLL ファイルで指定されたエントリポイントに関係なく、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2976f-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
<span data-ttu-id="2976f-117">`_CorDllMain` 関数は、オペレーティングシステムローダーによって直接呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2976f-117">The `_CorDllMain` function is called directly by the operating system loader.</span></span>
  
 <span data-ttu-id="2976f-118">詳細については、 [\_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)トピックの「解説」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2976f-118">For additional information, see the Remarks section in the [\_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2976f-119">［要件］</span><span class="sxs-lookup"><span data-stu-id="2976f-119">Requirements</span></span>  

 <span data-ttu-id="2976f-120">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2976f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2976f-121">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="2976f-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2976f-122">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="2976f-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2976f-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2976f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2976f-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="2976f-124">See also</span></span>

- [<span data-ttu-id="2976f-125">メタデータ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="2976f-125">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
