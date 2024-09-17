<script lang="ts">
    import * as Sheet from "@components/shadcn/ui/sheet";
    import Button from "@components/shadcn/ui/button/button.svelte";
</script>
    
   <Sheet.Root>
    <Sheet.Trigger asChild let:builder>
     <Button builders={[builder]} variant="outline">Open</Button>
    </Sheet.Trigger>
    <Sheet.Content side="right">
     <Sheet.Header>
      <Sheet.Title>Edit profile</Sheet.Title>
      <Sheet.Description>
       Make changes to your profile here. Click save when you're done.
      </Sheet.Description>
     </Sheet.Header>
     <div class="grid gap-4 py-4">
     </div>
     <Sheet.Footer>
      <Sheet.Close asChild let:builder>
       <Button builders={[builder]} type="submit">Save changes</Button>
      </Sheet.Close>
     </Sheet.Footer>
    </Sheet.Content>
   </Sheet.Root>