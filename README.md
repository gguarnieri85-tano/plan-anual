# Plan Anual / Calendario Familia

## Recuperar versiones

En Supabase → SQL Editor, ejecuta una vez:

```sql
create table if not exists plan_history (
  id bigint generated always as identity primary key,
  data jsonb,
  saved_at timestamptz default now()
);
alter table plan_history enable row level security;
create policy "anon full" on plan_history for all using (true) with check (true);
```

Después, en la app: Opciones → Historial de versiones.

Al abrir, la app carga siempre el plan más reciente de Supabase.
