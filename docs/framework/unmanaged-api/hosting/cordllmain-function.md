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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c509f475d5bf0105ece9791ee3e51d21c298a31f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666918"
---
# <a name="cordllmain-function"></a><span data-ttu-id="35a04-102">\_CorDllMain 関数</span><span class="sxs-lookup"><span data-stu-id="35a04-102">\_CorDllMain Function</span></span>

<span data-ttu-id="35a04-103">共通言語ランタイム (CLR) を初期化します、DLL アセンブリの CLR ヘッダーでマネージ エントリ ポイントを検索し、実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="35a04-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35a04-104">構文</span><span class="sxs-lookup"><span data-stu-id="35a04-104">Syntax</span></span>  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35a04-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="35a04-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="35a04-106">[in]読み込まれたモジュールのインスタンス ハンドル。</span><span class="sxs-lookup"><span data-stu-id="35a04-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="35a04-107">[in]DLL のエントリ ポイント関数が呼び出される理由を示します。</span><span class="sxs-lookup"><span data-stu-id="35a04-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="35a04-108">このパラメーターには、次の値のいずれかを指定できます。DLL\_PROCESS_ATTACH、DLL\_スレッド\_アタッチ、DLL\_スレッド\_ATTACH、または DLL\_プロセス\_デタッチします。</span><span class="sxs-lookup"><span data-stu-id="35a04-108">This parameter can be one of the following values: DLL\_PROCESS_ATTACH, DLL\_THREAD\_ATTACH, DLL\_THREAD\_ATTACH, or DLL\_PROCESS\_DETACH.</span></span> <span data-ttu-id="35a04-109">これらの値の説明については、次を参照してください。、`DllMain`プラットフォーム SDK のドキュメント。</span><span class="sxs-lookup"><span data-stu-id="35a04-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="35a04-110">[in]使用されていません。</span><span class="sxs-lookup"><span data-stu-id="35a04-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35a04-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="35a04-111">Return Value</span></span>  
 <span data-ttu-id="35a04-112">このメソッドが戻る`true`成功と`false`エラーが発生した場合。</span><span class="sxs-lookup"><span data-stu-id="35a04-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35a04-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="35a04-113">Remarks</span></span>  
 <span data-ttu-id="35a04-114">この関数は、DLL アセンブリのオペレーティング システム ローダーによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="35a04-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="35a04-115">実行可能アセンブリ ローダーの呼び出し、 [ \_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="35a04-115">For executable assemblies, the loader calls the [\_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="35a04-116">オペレーティング システム ローダーでは、DLL のファイルで指定されたエントリ ポイントに関係なく、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="35a04-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
<span data-ttu-id="35a04-117">`_CorDllMain`オペレーティング システム ローダーによって直接呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="35a04-117">The `_CorDllMain` function is called directly by the operating system loader.</span></span>
  
 <span data-ttu-id="35a04-118">詳細については、「解説」セクションを参照してください。、 [ \_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)トピック。</span><span class="sxs-lookup"><span data-stu-id="35a04-118">For additional information, see the Remarks section in the [\_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35a04-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="35a04-119">Requirements</span></span>  

 <span data-ttu-id="35a04-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="35a04-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35a04-121">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="35a04-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="35a04-122">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="35a04-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="35a04-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35a04-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35a04-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="35a04-124">See also</span></span>

- [<span data-ttu-id="35a04-125">メタデータ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="35a04-125">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
