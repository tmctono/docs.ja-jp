---
title: ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference メソッド
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetProbingAssembliesFromReference
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference method [.NET Framework hosting]
- GetProbingAssembliesFromReference method [.NET Framework hosting]
ms.assetid: aec05744-e8d4-44c6-b4a8-e583229ac34e
topic_type:
- apiref
ms.openlocfilehash: 21ebd0c64d6c8bbdac327258ad4c7ffec83a1ce9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504317"
---
# <a name="iclrassemblyidentitymanagergetprobingassembliesfromreference-method"></a><span data-ttu-id="fa67b-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference メソッド</span><span class="sxs-lookup"><span data-stu-id="fa67b-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference Method</span></span>
<span data-ttu-id="fa67b-103">指定した id 型のアセンブリによって参照されるアセンブリ id の[ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md)列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="fa67b-103">Gets an [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa67b-104">構文</span><span class="sxs-lookup"><span data-stu-id="fa67b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProbingAssembliesFromReference (  
    [in] DWORD   dwMachineType,  
    [in] DWORD   dwFlags,  
    [in] LPCWSTR pwzReferenceIdentity,  
    [out] ICLRProbingAssemblyEnum **ppProbingAssemblyEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa67b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fa67b-105">Parameters</span></span>  
 `dwMachineType`  
 <span data-ttu-id="fa67b-106">からWinnt.h で定義されているプロセッサアーキテクチャを指定する有効な値。</span><span class="sxs-lookup"><span data-stu-id="fa67b-106">[in] A valid value that specifies the processor architecture, as defined in WinNT.h.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="fa67b-107">から将来の拡張のために提供されます。</span><span class="sxs-lookup"><span data-stu-id="fa67b-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="fa67b-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT は、共通言語ランタイム (CLR) の現在のバージョンでサポートされている唯一の値です。</span><span class="sxs-lookup"><span data-stu-id="fa67b-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzReferenceIdentity`  
 <span data-ttu-id="fa67b-109">から通常、 [ICLRAssemblyIdentityManager:: GetBindingIdentityFromFile](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)または[ICLRAssemblyIdentityManager:: Getbinding fromstream](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)メソッドの呼び出しから返される、不透明なアセンブリバインド id。</span><span class="sxs-lookup"><span data-stu-id="fa67b-109">[in] An opaque assembly binding identity, typically returned from a call to the [ICLRAssemblyIdentityManager::GetBindingIdentityFromFile](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) or [ICLRAssemblyIdentityManager::GetBindingIdentityFromStream](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) method.</span></span>  
  
 `ppProbingAssemblyEnum`  
 <span data-ttu-id="fa67b-110">入出力`ICLRProbingAssemblyEnum`によって識別されるアセンブリによって参照されるアセンブリへの参照を格納する列挙子へのインターフェイスポインター `pwzReferenceIdentity` 。</span><span class="sxs-lookup"><span data-stu-id="fa67b-110">[out] An interface pointer to an `ICLRProbingAssemblyEnum` enumerator that contains references to the assemblies referenced by the assembly identified by `pwzReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa67b-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="fa67b-111">Return Value</span></span>  
  
|<span data-ttu-id="fa67b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fa67b-112">HRESULT</span></span>|<span data-ttu-id="fa67b-113">説明</span><span class="sxs-lookup"><span data-stu-id="fa67b-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fa67b-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="fa67b-114">S_OK</span></span>|<span data-ttu-id="fa67b-115">メソッドから正常に値が返されました。</span><span class="sxs-lookup"><span data-stu-id="fa67b-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="fa67b-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fa67b-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fa67b-117">CLR がプロセスに読み込まれていないか、CLR がマネージドコードを実行できない状態であるか、または呼び出しが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="fa67b-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fa67b-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fa67b-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fa67b-119">呼び出しがタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="fa67b-119">The call timed out.</span></span>|  
|<span data-ttu-id="fa67b-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fa67b-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fa67b-121">呼び出し元がロックを所有していません。</span><span class="sxs-lookup"><span data-stu-id="fa67b-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fa67b-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fa67b-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fa67b-123">ブロックされたスレッドまたはファイバーが待機しているときに、イベントが取り消されました。</span><span class="sxs-lookup"><span data-stu-id="fa67b-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fa67b-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fa67b-124">E_FAIL</span></span>|<span data-ttu-id="fa67b-125">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="fa67b-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fa67b-126">メソッドが E_FAIL を返す場合、そのプロセス内で CLR は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="fa67b-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fa67b-127">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="fa67b-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fa67b-128">要件</span><span class="sxs-lookup"><span data-stu-id="fa67b-128">Requirements</span></span>  
 <span data-ttu-id="fa67b-129">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa67b-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa67b-130">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fa67b-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fa67b-131">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="fa67b-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa67b-132">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa67b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa67b-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa67b-133">See also</span></span>

- [<span data-ttu-id="fa67b-134">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fa67b-134">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="fa67b-135">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fa67b-135">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="fa67b-136">ICLRProbingAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fa67b-136">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)
